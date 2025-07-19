2025-06-16 22:30

Status:

Tags: [[AWS]] [[storage]]

---
**What is an object?**
An object is a binary large Object or BLOB
- Think of the contents of your local computer - documents , photos videos
- can any size format, structure,or type
- does not depend on hierarchy for access or availability
- have rich metadata that provide additional content around the object
- some blob example are:
	- photos,music, raw or intermediate data from AI or ml pipelines, streaming and time series data from metrics, IOT device etc.

![[Pasted image 20250616224930.png]]

![[Pasted image 20250616232617.png]]

![[Pasted image 20250616232914.png]]

![[Pasted image 20250616233105.png]]


![[Pasted image 20250616233409.png]]


![[Pasted image 20250616233602.png]]


![[Pasted image 20250616235500.png]]
```bash
docker run -d \
--name minio \
-p 9000:9000 -p 9090:9090 \
-v ~/minio/data:/data \
-e "MINIO_ROOT_USER=root_user" \
-e "MINIO_ROOT_PASSWORD=root_password" \
quay.io/minio/minio server /data --console-address ":9090"
```



![[Pasted image 20250616235752.png]]

> [!important] 
> - Do not use the defaults in production
> - Do not use the root user for clients access, create a dedicated user for client access
> - create a user per application to access the perticular bucket

![[Pasted image 20250617001214.png]]

![[Pasted image 20250617001413.png]] 


## installation
```bash
pip3 install minio
```


![[Pasted image 20250619104405.png]]

```python
from minio import Minio


client = Minio(
	"localhost:9000",
	access_key="root_user",
	secret_key="root_password",
	secure=False,
)

# list bucket and bucket create data
buckets = client.list_buckets()
for bucket in buckets:
	print(bucket.name, bucket.creation_date)
```







## References