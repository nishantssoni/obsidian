

## 🚩 Purpose

Expose **Supabase Studio UI (port 3000) running in Docker** on your **Coolify server** locally on your LAN **without exposing to the public**, so you can:  
✅ Create tables, manage your DB, and use Supabase locally.

---

## 🩶 Step-by-Step Recovery and Setup

### 1️⃣ Get the Supabase Studio container ID

```bash
docker ps | grep supabase-studio
```

Note the **container ID**, e.g.:

```
82622bdf6c08
```

---
check network here
```bash
docker inspect 82622bdf6c08 | grep -A 50 '"Networks": {'
```



and connet to collify network
```
docker network connect coolify 82622bdf6c08
```

---
### 2️⃣ Get the **correct container IP for forwarding**

Run:

```bash
docker inspect 82622bdf6c08 | jq -r '.[0].NetworkSettings.Networks | to_entries[] | "\(.key): \(.value.IPAddress)"'
```

Example output:

```
a4kgko8w0cw0ckoo8880wws8: 10.0.6.14
coolify: 10.0.2.9
```

✅ **Use the `coolify` network IP** (`10.0.2.9` in this example).

---

### 3️⃣ Stop any stale `socat` forwards

```bash
docker ps --filter ancestor=alpine/socat
```

If any container shows up:

```bash
docker stop <container-id>
```

---

### 4️⃣ Start the `socat` forward with the correct IP

```bash
docker run --rm -d --network host alpine/socat TCP-LISTEN:3000,fork,reuseaddr TCP:<correct-IP>:3000
```

Example:

```bash
docker run --rm -d --network host alpine/socat TCP-LISTEN:3000,fork,reuseaddr TCP:10.0.2.5:3000
```


or if you want to always start the container use ::
```bash
docker run -d \
  --name supabase-studio-forward \
  --network host \
  --restart always \
  alpine/socat TCP-LISTEN:3000,fork,reuseaddr TCP:10.0.2.5:3000

```

---

### 5️⃣ Verify it is listening

```bash
ss -tulpn | grep 3000
```

✅ You should see:

```
tcp   LISTEN 0      5     0.0.0.0:3000       0.0.0.0:*    users:(("socat",pid=xxxxxx,fd=5))
```

---

### 6️⃣ Test locally on your Coolify server

```bash
curl -I http://localhost:3000
```

✅ You should get:

```
HTTP/1.1 200 OK
...
```

---

### 7️⃣ Access from your **laptop on the LAN**

#### Option A: Direct

Open in your browser:

```
http://<coolify-server-ip>:3000
```

(e.g., `http://192.168.1.6:3000`)

#### Option B: SSH Tunnel (encrypted)

```bash
ssh -L 3000:localhost:3000 nishant@nishant.local
```

Then open:

```
http://localhost:3000
```

in your browser.

---

## ✅ Troubleshooting Checklist

✅ If `curl` fails:

- Check container logs:
    
    ```bash
    docker logs <supabase-studio-container-id>
    ```
    
- Check if Supabase Studio is responding internally:
    
    ```bash
    docker exec -it <supabase-studio-container-id> curl -I http://localhost:3000
    ```
    
    ✅ Expect `HTTP/1.1 200 OK`.
    

✅ If your IP changes, repeat **Step 2** to get the new `coolify` network IP.

✅ If port `3000` is in use, change the `socat` port:

```bash
docker run --rm -d --network host alpine/socat TCP-LISTEN:3001,fork,reuseaddr TCP:<correct-IP>:3000
```

and access via `http://<coolify-server-ip>:3001`.

---

## ✅ Optional: Clean stop of `socat` forward

To stop the forward when not needed:

```bash
docker ps --filter ancestor=alpine/socat
docker stop <container-id>
```

---

## 🩶 Optional: Automate on boot with systemd

If you want, I can prepare a `socat-forward.service` systemd file so you **never need to repeat manually** on reboot while keeping your Supabase Studio local and safe.

---

## ✅ Summary:

✅ Always fetch the **correct container IP (`10.0.2.9` type)**.  
✅ Restart `socat` cleanly using that IP.  
✅ Verify with `curl`.  
✅ Access locally via direct IP or SSH tunnel for Supabase Studio workflow.

---

If you want this in **Markdown for your Obsidian or offline notes**, let me know.