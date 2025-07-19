tags:
[[settings]] [[n8n]]

---

Follow these precise steps to **enable `n8n` inside Docker to access `Ollama` running on your Raspberry Pi host** using `http://host.docker.internal:11434`.

---

## ✅ 1️⃣ Add `extra_hosts` to `n8n` in `docker-compose.yml`

Add the following under your `n8n` service:

```yaml
extra_hosts:
  - "host.docker.internal:host-gateway"
```

This allows your `n8n` container on **Linux** to resolve `host.docker.internal` and access services on your Pi host.

---

## ✅ 2️⃣ Configure Ollama to listen on `0.0.0.0`

### Step 1: Edit the systemd service for Ollama

```bash
sudo nano /etc/systemd/system/ollama.service
```

---

### Step 2: Add the environment variable

Inside the `[Service]` section, below the existing `PATH` environment, add:

```ini
[Service]
...
Environment="PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"
Environment=OLLAMA_HOST=0.0.0.0:11434
```

This ensures **Ollama will listen on all interfaces (`0.0.0.0`)** instead of only `127.0.0.1`.

---

### Step 3: Reload systemd and restart Ollama

```bash
sudo systemctl daemon-reload
sudo systemctl restart ollama
```

---

## 🚀 You can now use:

```
http://host.docker.internal:11434
```

in your **n8n workflows** to connect seamlessly to **Ollama running on your Raspberry Pi host**.