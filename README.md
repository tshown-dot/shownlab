# Shown Lab (`shownlab.com`)

The official landing page, portfolio, and subdomain hub for **Shown Lab** — bridging applied machine learning research, experimental prototypes, and specialized AI consulting.

---

## 🚀 Deployment on Render

This site is structured as a **Static Site** on Render:
* **Cost:** 100% Free
* **Uptime:** Never goes to sleep (unlike free backend containers)
* **Custom Domains:** Supports `shownlab.com` and `www.shownlab.com` with automated free SSL.

### Render Configuration
* **Name:** `shownlab` (or `shownlab-hub`)
* **Branch:** `main`
* **Root Directory:** (leave blank / root)
* **Build Command:** (leave blank)
* **Publish Directory:** `.`

---

## 🌐 Namecheap DNS Setup for `shownlab.com`

In **Namecheap** -> **Domain List** -> **shownlab.com** -> **Advanced DNS**:

| Type | Host | Value | TTL |
| :--- | :--- | :--- | :--- |
| **CNAME Record** | `www` | `<your-render-app-name>.onrender.com` | Automatic |
| **ALIAS Record** / **ANAME** | `@` | `<your-render-app-name>.onrender.com` | Automatic |

*(Render also provides standard A records if you prefer A records over ALIAS for the `@` root).*

---

## 🛰 Adding Future Subdomain Services (e.g. `agent.shownlab.com`)

When you build a new Python / Docker / Web Service on Render:
1. Deploy the new service on Render.
2. In the new service's **Settings** -> **Custom Domains**, add `agent.shownlab.com`.
3. In **Namecheap** -> **Advanced DNS**, add a new **CNAME Record**:
   * **Host:** `agent`
   * **Value:** `<new-service-name>.onrender.com`
