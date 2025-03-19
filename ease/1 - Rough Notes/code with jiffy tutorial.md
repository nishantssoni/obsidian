2025-03-19 21:24

Status:

Tags:

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


start from 41 min

---
## References