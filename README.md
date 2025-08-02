# 🎬 Jellyfin + Tailscale Media Server on macOS

A private, self-hosted alternative to Netflix — built with Jellyfin and Tailscale on macOS. Stream your movies, TV shows, and music securely across all your devices with no subscriptions, ads, or public exposure.

---

## 📌 Project Overview

This setup creates a **personal media streaming server** using:
- 🎥 [Jellyfin](https://jellyfin.org) – an open-source media server
- 🔐 [Tailscale](https://tailscale.com) – a secure, WireGuard-powered VPN
- 🍎 macOS as the host machine

You can stream your content **locally and remotely** using your phone, tablet, browser, smart TV, or media player — all encrypted and private.

---

## 🛠️ Technologies Used

| Technology     | Role / Purpose                                   |
|----------------|--------------------------------------------------|
| **Jellyfin**    | Media server for personal streaming              |
| **Tailscale**   | Mesh VPN for secure remote access                |
| **WireGuard**   | Lightweight encrypted VPN protocol (via Tailscale) |
| **macOS**       | Host OS                                          |
| **Port 8096**   | Default port for Jellyfin web interface          |


---

## 🧑‍💻 System Environment

| Component      | Details                               |
|----------------|----------------------------------------|
| OS             | macOS 10.15+ or newer                 |
| CPU            | Intel i5 / Apple M1 or better         |
| RAM            | Minimum 4 GB (8 GB recommended)       |
| Storage        | Local or external media storage       |
| Network        | Wi-Fi or Ethernet + Tailscale VPN     |
| Dependencies   | .NET 6+, Tailscale app, optional Homebrew |


---

## 🚀 Setup Instructions

### ✅ 1. Install Jellyfin on macOS
- Download the `.pkg` installer from [jellyfin.org/downloads](https://jellyfin.org/downloads/)
- Install and launch the server
- Access from local browser:
http://localhost:8096

![Jellyfin UI](/images/\ .png)
![Jellyfin UI](/images/e0a87856b69877660cb539a2a69dc60452aecc124bfc97116133877b45c2701e.png)
![Jellyfin UI](/images/172f7eec117ffc94c592bcde0458c9fa97b1a0684876737203c09085f555d06c.png)
![Jellyfin UI](/images/c94a31989ce61edb7f6bde2bf4da4f3e80a8a6b334b52fe6d743206dd087ed2d.png)
![Jellyfin UI](/images/3db3b67bfda05e1aa8087d2978e2288338c31631f2a4e246569ab034bfc2f961.png)
![Jellyfin UI](/images/223a6972096016dcc58d27a91280f5326c86aad4a3a6b7f45629656584597579.png)
![Jellyfin UI](/images/d2e0e28a56e0df796a74f0c2bce3f523839b51e3415370716823a75066fae65c.png)
![Jellyfin UI](/images/d3bdb6284bcb42f4383f75db612e1a125febbbbd0c7d372a9579a04bd505d7fd.png)


---

### ✅ 2. Configure Media Libraries
- Create folders for content: `~/Media/Movies`, `~/Media/TV`, etc.
- In Jellyfin, go to **Dashboard → Libraries → Add Media Library**

![Library Setup](/images/5a2f6c9942ab8fa52b93956822298cbea60ba334d73e1783fbd1e581b57a14db.png)
![Library Setup](/images/8b5485c0bca04bc23e412933666596ee11b6a4e7a561a3d0901b5e44694f359b.png)
---

### ✅ 3. Install and Configure Tailscale
- Download Tailscale from [tailscale.com/download](https://tailscale.com/download)
![Download UI](/images/e0be22e05f3a8f8af4bdf7b10af2b8ab95c66e0709d5add0cec678fa904f633d.png)
- Log in and connect the device
- Get your Tailscale IP:

![Tailscale IP](/images/tailscale-ip1.png)
---

### ✅ 4. Access Remotely via Tailscale

From any other device with Tailscale installed, access:
http://100.x.x.x:8096
(Optional) Enable MagicDNS for cleaner access:
http://your-mac-hostname.ts.net:8096

🌐 Local Access
On host machine:
http://localhost:8096
On same LAN:
http://<your-local-ip>:8096
---

### ✅ Testing Checklist

| Task                                | Status   |
|-------------------------------------|----------|
| Jellyfin accessible on localhost    | ✅       |
| Media libraries added               | ✅       |
| Remote access via Tailscale IP      | ✅       |
| Tested from mobile device           | ✅       |
| MagicDNS hostname access (optional)| ✅ / ❌   |

---

### 🔐 Security Notes

- 🔒 No public IP exposure required  
- 🔐 All traffic encrypted with WireGuard via Tailscale  
- 🧑‍💻 Jellyfin supports user login with password  
- 🎯 Tailscale ACLs can limit which devices can access the server  

---

### 📱 Supported Clients

| Platform   | Method                                  |
|------------|------------------------------------------|
| Desktop    | Web browser, VLC, MPV                   |
| Mobile     | Jellyfin app or browser                 |
| Smart TVs  | Jellyfin TV app, DLNA, Plex app         |

---

### 🔧 Optional Enhancements

| Feature                     | Description                                      |
|-----------------------------|--------------------------------------------------|
| Reverse Proxy (Caddy/Nginx)| Add HTTPS or custom domains (advanced)          |
| Auto-start on Boot          | Start Jellyfin + Tailscale on login             |
| Plugins & Themes            | Metadata enhancers, intro skip, etc.            |
| Device Sharing              | Share Jellyfin access securely via Tailscale    |

---

## 📚 What I Learned

This project helped me develop practical skills in:

- 🧠 Hosting a private, customizable streaming platform  
- 🔐 Securing access using Tailscale without exposing ports  
- 🖥️ Installing and managing services on macOS  
- 🌍 Understanding networking concepts like mesh VPNs and MagicDNS  
- 🧪 Troubleshooting connectivity, firewall, and library issues  


---

### 📁 Project Outcome

With this setup, I now have:

- ✅ A secure, private media server accessible from anywhere  
- 💸 Zero monthly costs, no ads, and no external trackers  
- 🎛️ Full control over my library, user access, and playback  
- 🧠 An understanding of self-hosting, VPNs, and server management  

---

## 📎 Resources

- [Jellyfin Docs](https://jellyfin.org/docs/)
- [Tailscale Docs](https://tailscale.com/kb/)
- [MagicDNS Guide](https://tailscale.com/kb/1081/magicdns/)

---

## ✨ License

This project uses only open-source tools and has no proprietary dependencies. You are free to adapt and extend this for personal or educational use.
📌 Want to contribute improvements?
Fork this repo, clone it, and improve it for your setup or share with friends & family. Happy streaming! 🎬

---

