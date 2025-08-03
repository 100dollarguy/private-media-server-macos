# 🎬 My Personal Media Server – Jellyfin + Tailscale on macOS

I built a secure, self-hosted media streaming server using [Jellyfin](https://jellyfin.org) and [Tailscale](https://tailscale.com), all running from my macOS machine. Now I can stream movies, TV shows, and music from anywhere — without subscriptions, ads, or exposing anything to the public internet.

---

## 📌 Why I Built This

I wanted a simple, private way to enjoy my media on all my devices — at home or on the go. With this setup, everything stays under my control: no third parties, no data collection, just me and my content.

---

## 🛠️ Tech Stack

| Tool          | Purpose                                       |
|---------------|-----------------------------------------------|
| **Jellyfin**  | Open-source media server                      |
| **Tailscale** | VPN for secure remote access                  |
| **WireGuard** | Encrypted mesh network (via Tailscale)        |
| **macOS**     | Host machine for the server                   |
| **Port 8096** | Default Jellyfin web interface port           |

---

## 💻 System Details

| Component      | Description                          |
|----------------|--------------------------------------|
| OS             | macOS 10.15+                         |
| Hardware       | Intel i5 / Apple M1, 8 GB+ RAM       |
| Storage        | Local or external (for media)        |
| Network        | Wi-Fi or Ethernet + Tailscale VPN    |
| Dependencies   | .NET 6+, Tailscale, Homebrew (optional) |

---

## 🚀 How I Set It Up

### ✅ 1. Installed Jellyfin on macOS

I downloaded the `.pkg` installer from [jellyfin.org/downloads](https://jellyfin.org/downloads/), installed it like any other app, and launched the server.


![Jellyfin UI](/images/e0a87856b69877660cb539a2a69dc60452aecc124bfc97116133877b45c2701e.png)  
![Jellyfin UI](/images/172f7eec117ffc94c592bcde0458c9fa97b1a0684876737203c09085f555d06c.png)  
![Jellyfin UI](/images/c94a31989ce61edb7f6bde2bf4da4f3e80a8a6b334b52fe6d743206dd087ed2d.png) 

I accessed it from my local browser at:

http://localhost:8096

Here’s what it looked like once it was up and running:
 
![Jellyfin UI](/images/3db3b67bfda05e1aa8087d2978e2288338c31631f2a4e246569ab034bfc2f961.png)  
![Jellyfin UI](/images/223a6972096016dcc58d27a91280f5326c86aad4a3a6b7f45629656584597579.png)  
![Jellyfin UI](/images/d2e0e28a56e0df796a74f0c2bce3f523839b51e3415370716823a75066fae65c.png)  
![Jellyfin UI](/images/d3bdb6284bcb42f4383f75db612e1a125febbbbd0c7d372a9579a04bd505d7fd.png)  

---

### ✅ 2. Set Up My Media Library

I organized my files into folders like:

~/Media/Movies
~/Media/TV

Then, in the Jellyfin dashboard, I went to **Dashboard → Libraries → Add Media Library** and linked those folders.

Here's the library setup in action:

![Library Setup](/images/5a2f6c9942ab8fa52b93956822298cbea60ba334d73e1783fbd1e581b57a14db.png)  
![Library Setup](/images/8b5485c0bca04bc23e412933666596ee11b6a4e7a561a3d0901b5e44694f359b.png)  
![Library Setup](/images/3df054a9450ca2c303b1ccc352ea92f5c50263338611a2aefdcf7f01abeda631.png)  
![Library Setup](/images/694eb240d4a08e3b71ea2ebf33f7883b47598f7c8143746c131d8bbf4ad5b9ec.png)  
![Library Setup](/images/b5b31bf564e8f3f64128deb6cf53a6aa1c59b2d2a13ce16f28e0df7d1f078132.png)  

---

### ✅ 3. Installed Tailscale for Secure Remote Access

I installed Tailscale from [tailscale.com/download](https://tailscale.com/download), logged in with my account, and added my Mac as a device in my private mesh network.

![Download UI](/images/e0be22e05f3a8f8af4bdf7b10af2b8ab95c66e0709d5add0cec678fa904f633d.png)

Once it connected, I grabbed the Tailscale IP from the app:

![Tailscale IP](/images/tailscale-ip.png)

---

### ✅ 4. Accessed My Server Remotely

From any of my other devices (with Tailscale installed), I could now connect to:

http://100.x.x.x:8096

To make it even cleaner, I enabled MagicDNS and used:

http://your-mac-hostname.ts.net:8096

### 🌐 Access Points

| Location        | URL                                |
|-----------------|-------------------------------------|
| Localhost       | `http://localhost:8096`            |
| Same Network    | `http://<your-local-ip>:8096`      |
| Remote (VPN)    | `http://100.x.x.x:8096`            |
| MagicDNS (opt.) | `http://your-mac-hostname.ts.net`  |

---

## ✅ Testing Checklist

| Task                                 | Status |
|--------------------------------------|--------|
| Jellyfin accessible locally          | ✅     |
| Libraries created and scanned        | ✅     |
| Remote access with Tailscale         | ✅     |
| Streaming from mobile & smart TV     | ✅     |
| MagicDNS for cleaner URL (optional)  | ✅ / ❌  |

---

## 🔐 Why It’s Secure

- No open ports or public IPs  
- All traffic routed through encrypted WireGuard tunnels (Tailscale)  
- Jellyfin uses user authentication  
- Tailscale ACLs restrict which devices can reach the server  

---

## 📱 Works On All My Devices

| Device Type | How I Use It                          |
|-------------|----------------------------------------|
| Desktop     | Web browser, MPV, VLC                 |
| Phone/Tablet| Jellyfin app or web browser           |
| Smart TV    | Jellyfin TV app, DLNA client, Plex app|

---

## 🔧 Extras I Explored

| Feature               | What It Did                             |
|-----------------------|------------------------------------------|
| Auto-start on login   | Ensures Jellyfin + Tailscale run always |
| Plugins & themes      | Metadata tools, intro skip, UI tweaks   |
| Shared access         | Family can stream over Tailscale safely |

---

## 💡 What I Learned

This project taught me a lot about:

- Hosting and managing a personal server  
- Securing remote access via mesh VPN  
- File organization and metadata handling  
- Network configuration on macOS  
- Troubleshooting cross-device compatibility  

---

## 🎯 Final Result

What I ended up with is:

- ✅ A fully private, secure media server  
- 🎬 A Netflix-like experience with zero subscriptions  
- 🌍 Remote access with no port forwarding  
- 💻 Full control over everything: users, content, and streaming

---

## 📎 Resources I Used

- [Jellyfin Docs](https://jellyfin.org/docs/)
- [Tailscale Docs](https://tailscale.com/kb/)
- [MagicDNS Setup](https://tailscale.com/kb/1081/magicdns/)

---

## ✨ License

This project is licensed under the [MIT License](LICENSE).  
You're free to use, modify, and share it — personally or commercially.

Feel free to fork it, improve it for your own setup, or share with others!
