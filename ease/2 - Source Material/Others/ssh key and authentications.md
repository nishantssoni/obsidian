# removing old ssh keys
Here is a **safe, complete guide to clean _all_ SSH keys from your system and servers**:

---

## 🧹 1️⃣ Remove **all SSH keys locally**

Run:

```bash
rm -f ~/.ssh/id_rsa ~/.ssh/id_rsa.pub ~/.ssh/id_ecdsa ~/.ssh/id_ecdsa.pub ~/.ssh/id_ed25519 ~/.ssh/id_ed25519.pub
```


```shell
truncate -s 0 ~/.ssh/authorized_keys
```


---

## 🧹 2️⃣ Clean your **known_hosts**

This removes all cached host fingerprints:

```bash
rm -f ~/.ssh/known_hosts ~/.ssh/known_hosts.old
```

---

## 🧹 3️⃣ Clean `authorized_keys` on **your server**

SSH into your server using **password**:

```bash
ssh user@server
```

then run:

```bash
> ~/.ssh/authorized_keys
```

or

```bash
truncate -s 0 ~/.ssh/authorized_keys
```

This removes **all keys from your server**, ensuring _no existing key will work_.

---

## ✅ Result:

- **No SSH keys left locally** (fully clean slate).
    
- **No authorized keys on your server**.
    
- **SSH will require passwords for login** until you generate and add a new key.
    

---

# generating ssh