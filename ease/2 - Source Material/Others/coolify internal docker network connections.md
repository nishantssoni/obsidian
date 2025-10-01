Here is a **clean, reusable workflow** to **debug and fix n8n ↔ Postgres connectivity issues inside Docker (Coolify or any self-hosted stack)** whenever `getaddrinfo EAI_AGAIN` or similar errors occur:

---

## 🚀 **n8n ↔ Postgres Connectivity Debug + Fix Workflow**

### 1️⃣ **Identify your containers**

List containers:

```bash
docker ps
```

Identify:

- n8n container ID (e.g., `abf45e06429b`)
    
- Postgres container ID (e.g., `zgg8ko444go8g0cc8c48o080`)
    

---

### 2️⃣ **Check which Docker networks they are connected to**

For **Postgres:**

```bash
docker inspect <postgres_container_id> | grep -A 20 '"Networks": {'
```

Example:

```bash
docker inspect 59cfb16ebf12 | grep -A 20 '"Networks": {'
```

For **n8n:**

```bash
docker inspect <n8n_container_id> | grep -A 20 '"Networks": {'
```

Example:

```bash
docker inspect abf45e06429b | grep -A 20 '"Networks": {'
```

---

### 3️⃣ **Interpret the output**

- Note the **network name(s)** under `"Networks": {`.
    
- Note the **`"IPAddress"`** for fallback direct IP connection.
    

✅ If **both containers share at least one common network**, you can use:

```
Host: <postgres_container_name>
```

or

```
Host: <postgres_internal_IP>
```

inside n8n Postgres credentials.

❌ If they **do not share a network**, proceed to the next step.

---

### 4️⃣ **Connect n8n to Postgres’s network**

Syntax:

```bash
docker network connect <postgres_network_name> <n8n_container_id>
```

Example:

```bash
docker network connect coolify abf45e06429b
```

✅ This attaches **n8n to the Postgres’s network while preserving its existing network**.

---

### 5️⃣ **Test the connection in n8n**

In your **n8n Postgres credentials**:

- **Host:** use the Postgres container name (`<container_name>`) or IP.
    
- **Port:** `5432`
    
- **User/Password/Database:** your configured values.
    

Click **Test**.

✅ If successful, your n8n ↔ Postgres workflow will now work.

---

## ✅ Optional fallback: Use direct IP if DNS fails

If DNS resolution is still an issue:

- Use the `"IPAddress"` of the Postgres container:
    
    ```bash
    docker inspect <postgres_container_id> | grep '"IPAddress"'
    ```
    
- Enter this IP in **Host** within n8n credentials.
    

---

## ⚠️ **Persistence considerations**

Manual `docker network connect`:

- **Does not persist** if you redeploy containers (Coolify update, container recreation).
    
- For **permanent fixes**:
    
    - Deploy **n8n and Postgres under the same Coolify project** to auto-share the network.
        
    - If Coolify supports advanced networking, configure shared networks explicitly.
        

---

## 🛠️ **Quick reference snippet for your notes**

```bash
# List containers
docker ps

# Check networks
docker inspect <postgres_container_id> | grep -A 20 '"Networks": {'
docker inspect <n8n_container_id> | grep -A 20 '"Networks": {'

# Attach n8n to Postgres's network if needed
docker network connect <postgres_network_name> <n8n_container_id>
```

---

## 🪐 **Benefits of using this workflow**

✅ Quickly debug **n8n → Postgres connectivity** reliably.  
✅ Works for **any Docker-based local or cloud deployment** (Coolify, Portainer, bare Docker).  
✅ Keeps your projects running without needing to expose Postgres externally.

---

If you want, I can generate:  
✅ A **one-file `n8n-troubleshoot.sh` utility script** to automate these checks and commands interactively whenever you face this issue. Let me know if you would like it.