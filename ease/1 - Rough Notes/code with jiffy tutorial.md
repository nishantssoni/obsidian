2025-03-19 21:24

Status:

Tags: [[matplotlib]] #hard 

[project for this note](https://github.com/nishantssoni/open_help_bot)

---

### the basic python code for ollama api 

```python
from openai import OpenAI
import os
from dotenv import load_dotenv

load_dotenv()

client = OpenAI(
api_key=os.getenv("TOKEN"),
base_url=os.getenv("BASE_URL"),
)
model_name = os.getenv("MODEL_NAME")


response = client.chat.completions.create(
model=model_name,
messages=[
{"role": "user", "content": "what is the capital of india?"}
],
temperature=0.0,
top_p=0.8,
max_tokens=100)

print(response.choices[0].message.content)
```

---
### Prompt Enginnering Technique

it going to enhance the output of the models make it more accurate and more structured we can put it in a structured format so we can put it to the agent to agent also we can put it on the databases.


#### 1. system prompt 
It is the prompt where we defined how the chat bot should behave.
```python
system_prompt ="""
You are a chatbot that answers questions about capital of the contries.

Your outputs should be in the list of structured json format exactly like the one below. you are not allowed to write anything other that json object and also dont use newlines:

[{
"country": the country you will get capital of,
"capital": the capital of the country
}]
"""

messages = [{"role": "system", "content": system_prompt}]
messages.append({"role": "user", "content": "capital city of china"})
response = get_chat_response(client, model_name, messages) 
json_response = json.loads(response)
print(json_response)
```
output: 
`[{'country': 'China', 'capital': 'Beijing'}]`

#### 2.Input structuring
here we structure the inputs from the user so the at the end the prompt can be easily and clearly understand by LLMs

![[Pasted image 20250319222438.png]]
```python
messages = [{"role": "system", "content": system_prompt}]
messages.append({"role": "user", "content": user_input})
response = get_chat_response(client, model_name, messages)
json_response = json.loads(response)

print(json_response)
```

---

#### Give the model time to think (Chain of thoughts)

we give the model extra step or prompt to think so we can get  a better result.

here below is avg user prompt
```python
user_prompt = """
Calculate the result of this equation 259/2*8654+91072*33-12971

Your output should be in a structured json format exactly like the one bellow. You are not allowed to write anythinkg other than the json object:
{
	result: The final number resulted from calculating the equation above
}
"""
messages = [{"role": "user", "content": user_prompt}]
response = get_chat_response(client, model_name, messages)
print(response)
```
output:
`{"result": -1234567}`
==It has high error==

**if we modify then it the error is far less then before**
```python
user_prompt = """
Calculate the result of this equation 259/2*8654+91072*33-12971

Your output should be in a structured json format exactly like the one bellow. You are not allowed to write anythinkg other than the json object:

{

steps: This is where you solve the equation bit by bit following the BODMAS order of operations. You need to show your work and calculate each step leading to the final result. Feel free to write in free text.

result: The final number resulted from calculating the equation above

}

"""

messages = [{"role": "user", "content": user_prompt}]
response = get_chat_response(client, model_name, messages,max_tokens=1000)
print(response)
```

output:
`{
  "steps": "First, we divide 259 by 2: 259/2 = 129.5\nNext, we multiply 8654 by 129.5: 8654*129.5 = 1,119,301\nThen, we multiply 91072...",
  "result": 4109426
}`

==The error is faar less==

---

#### RAG

RAG is a method used in AI to improve responses by retrieving relevant information from a database before generating an answer. Instead of relying only on what the model was trained on, it fetches up-to-date or domain-specific data to give better results.

#### **Example:**

Imagine you ask an AI:  
👉 _"What is the latest research on AI ethics?"_
- A normal AI model might give a generic answer based on its training.
- A **RAG-powered AI** first **retrieves** recent papers from an online database, then **generates** a response using that fresh data.

💡 **Why use RAG?**
- Provides **more accurate** and **up-to-date** responses.
- Helps in **domain-specific** knowledge (e.g., legal, medical).
- Reduces hallucinations (wrong or made-up answers).

🚀 **Real-world Use Cases:**
- Chatbots pulling latest product details.
- AI assistants fetching current stock prices.
- Research tools summarizing recent studies.


**the model is not trained on iphone 16 so if we ask the question the model doesn't give the information**
```python
user_prompt = """
What's new in iphone 16?
"""
messages = [{"role": "user", "content": user_prompt}]
response = get_chat_response(client, model_name, messages,max_tokens=100)
print(response)
```
output:
`There is no official announcement`

**But if we provide context then we can generate from that context**
```python
iphone_16 ="""
The iPhone 16 series marks a significant leap forward in Apple's smartphone technol.....
"""

samsung_s24="""
The Samsung Galaxy S24 Ultra represents a significant a......
"""

user_prompt = f"""
{iphone_16}
What's new in iphone 16?

"""

messages = [{"role": "user", "content": user_prompt}]
response = get_chat_response(client, model_name, messages,max_tokens=100)
print(response)
```
output:
`According to the text, some of the new features and improvements`


code for using embedding feature from using bge model this model convert text to embedding vectors from which we can extract only those information from the data which is relevent by comparing.

e.g if i want iphone 16 information then we convert the prompt and find the iphone data from the dataset by using RAG, we convert the prompt and then by comparing from dataset we find the information from the dataset.

first install this
```bash
conda create -n faiss_env python=3.9
conda activate faiss_env
conda install -c pytorch faiss-gpu cudatoolkit=11.3
```


```python
from sentence_transformers import SentenceTransformer
from huggingface_hub import snapshot_download
import faiss
import numpy as np

# Download the model to a local directory
local_model_path = "./bge-small-en"
snapshot_download(repo_id="BAAI/bge-small-en", local_dir=local_model_path)

# Now load the locally saved model
model = SentenceTransformer(local_model_path)


# Load the BGE-Small model and store in cache
# model = SentenceTransformer("BAAI/bge-small-en")
```


_now embedding and storing to a faiss_
```python
data = [iphone_16, samsung_s24]
user_prompt = f"""What's new in iphone 16?"""

# Generate embeddings
# BGE models require normalization
embeddings = model.encode(data, normalize_embeddings=True) 

# Store in FAISS index
dimension = embeddings.shape[1]
index = faiss.IndexFlatL2(dimension)
index.add(np.array(embeddings))

# Save FAISS index
faiss.write_index(index, "bge_vector_store.index")
print("Embeddings stored successfully!")
```


_now retriving the context using the given prompt_

```python
# Load FAISS index
index = faiss.read_index("bge_vector_store.index")

# Encode a query
query = "android"
query_embedding = model.encode([query], normalize_embeddings=True)

  

# Search for top 1 similar results
D, I = index.search(np.array(query_embedding), k=1)

# Print closest matches
print(f"Closest matches: {[data[i] for i in I[0]]}")
```
ouput:
Closest matches: "\nThe Samsung Galaxy S24 Ultra represents .....



_fill code_
```python
from openai import OpenAI
import os
from dotenv import load_dotenv
import json
load_dotenv()


client = OpenAI(
api_key=os.getenv("TOKEN"),
base_url=os.getenv("BASE_URL"),
)
model_name = os.getenv("MODEL_NAME")


def get_chat_response(client, model_name, messages, temprature=0.0, top_p=0.8, max_tokens=100):

	input_messages = []
	for message in messages:
	input_messages.append({"role": message["role"], "content": message["content"]})
	
	response = client.chat.completions.create(
	model=model_name,
	messages=input_messages,
	temperature=temprature,
	top_p=top_p,
	max_tokens=max_tokens

)

  

return response.choices[0].message.content
```



### Recommendation engine traning
![[Pasted image 20250322205206.png]]

![[Pasted image 20250322205316.png]]
 `^quantify the strength of an association rule.`


![[Pasted image 20250322205618.png]]
![[Pasted image 20250322205750.png]]

---
 rule

## References
 [[Long Format vs Wide format data]]
 [[pivot and pivot table]]
 [[Apriori recommendation engine]]