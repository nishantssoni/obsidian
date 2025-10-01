
see all the networks connected
```bash
docker inspect container_id | grep -A 50 '"Networks": {'

```



type docker ps
and see the kong name

---

## **1️⃣ Correct Internal Host for Supabase (Kong)**

Your Kong container name is:supabase-kong-a4kgko8w0cw0ckoo8880wws8

```
supabase-kong-a4kgko8w0cw0ckoo8880wws8
```

Thus, **in n8n:**

**Host:**

```
http://supabase-kong-a4kgko8w0cw0ckoo8880wws8:8000
```

✅ This uses the **exact container name** to resolve internally within the Docker network in Coolify.

---

## **2️⃣ Port Confirmation**

Kong listens on:

```
8000/tcp
```

✅ So `:8000` is correct.

---

## **3️⃣ Service Role Secret**

Use your **`SUPABASE_SERVICE_ROLE_KEY`** exactly as it is from your Supabase environment or Studio settings.

Example:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

✅ Do **not use the anon key** for backend operations.

---

## **✅ Final Configuration in n8n:**

|Setting|Value|
|---|---|
|**Host**|`http://supabase-kong-a4kgko8w0cw0ckoo8880wws8:8000`|
|**Service Role Secret**|`<your_SUPABASE_SERVICE_ROLE_KEY>`|

---

## **4️⃣ Test Connectivity**

### Option A: Using n8n HTTP Request Node:

- **Method:** `GET`
    
- **URL:** `http://supabase-kong-a4kgko8w0cw0ckoo8880wws8:8000/rest/v1/`
    
- **Headers:**
    
    - `apikey: <your_SUPABASE_SERVICE_ROLE_KEY>`
        
    - `Authorization: Bearer <your_SUPABASE_SERVICE_ROLE_KEY>`
        

✅ Execute to verify you get a JSON response (or auth error if key wrong).

---

### Option B: Shell test inside n8n container

```bash
docker exec -it n8n-rwcc0gc440gc808wcskco884 sh
apk add --no-cache curl
curl -i -H "apikey: <your_SUPABASE_SERVICE_ROLE_KEY>" \
     -H "Authorization: Bearer <your_SUPABASE_SERVICE_ROLE_KEY>" \
     http://supabase-kong-a4kgko8w0cw0ckoo8880wws8:8000/rest/v1/
```

✅ If it connects, your DNS + connectivity is working.

---

## ✅ Why this fixes your “DNS server returned an error”:

Using `http://kong:8000` **fails** because:

- The actual container name (`supabase-kong-a4kgko8w0cw0ckoo8880wws8`) is what Docker resolves internally in your Coolify project network.
    

Using the exact container name fixes internal DNS resolution inside Coolify’s shared network.

---

If you want:  
✅ I can also generate a **ready-to-import n8n workflow** for Supabase read/insert tests to validate your connectivity instantly. Let me know!