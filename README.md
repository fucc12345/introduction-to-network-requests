# 🔍 Network Request Interception Guide  
## Analyze Your Device's Connections Like a Pro 🧠🌐  

> **By Techie, with ❤️**

---

## 📖 Table of Contents  

- [📋 Overview](#-overview)  
- [⚙️ Prerequisites](#️-prerequisites)  
- [📲 App Installation Guide](#-app-installation-guide)  
- [🚦 Start Capturing Traffic](#-start-capturing-traffic)  
- [🧪 Certificate Installation](#-certificate-installation)  
- [🚫 Warning About App Bypasses](#-warning-about-app-bypasses)  
- [🛠️ Possible Fixes for Certificate Pinning](#️-possible-fixes-for-certificate-pinning)  
- [📊 How to Analyze Requests](#-how-to-analyze-requests)  
- [📺 Android TV and Other Devices](#-android-tv-and-other-devices)  
- [🔗 Extracting M3U and Other Links](#-extracting-m3u-and-other-links)  
- [📚 Glossary of Headers](#-glossary-of-headers)  
- [📌 Final Thoughts](#-final-thoughts)  
- [⚠️ Disclaimer](#️-disclaimer)  
- [🧑‍💻 Author](#-author)

---

## 📋 Overview  

Apps like **Reqable** and **Fiddler Classic** are powerful tools that let you intercept and analyze the **network traffic** going in and out of your device. This can help you understand which servers your apps are communicating with and extract useful information such as API URLs, M3U playlists, headers, and more. 🌐📡

---

## ⚙️ Prerequisites  

Here’s what you’ll need to get started:

| Device Type | Tool to Use |
|-------------|-------------|
| **Android** | ✅ Reqable App |
| **Windows** | ✅ Fiddler Classic |
| **iOS**     | ✅ Reqable App (with trusted certificate) |

---

## 📲 App Installation Guide  

### For Android:  
1. Go to the [official Reqable site](https://reqable.com) or Play Store (if available).  
2. Download and install the app.  
3. Open it and grant necessary permissions.

### For Windows:  
1. Visit [Fiddler Classic's official website](https://www.telerik.com/fiddler).  
2. Download and install Fiddler Classic.  
3. Open it and start capturing traffic.

### For iOS:  
1. Install **Reqable** via official TestFlight or AltStore.  
2. Set up the VPN configuration as guided in the app.

---

## 🚦 Start Capturing Traffic  

1. Open Reqable or Fiddler.
2. Press **Start Capture** 🟢.
3. The app will create a **local VPN** on your device.
4. This VPN is only for intercepting traffic (no external data collection).

---

## 🧪 Certificate Installation  

> ⚠️ **Important Step!**  

To view **HTTPS requests**, you MUST install the interception certificate provided by Reqable or Fiddler:

### Android:
- Follow the in-app prompt in Reqable to install its certificate.

### Windows:
- In Fiddler, go to:
  - **Tools > Options > HTTPS > Enable HTTPS Decryption**
  - Click **Install Certificate**

### iOS:
- Manually trust the certificate in:
  - **Settings > General > About > Certificate Trust Settings**

---

## 🚫 Warning About App Bypasses  

Many modern apps implement **certificate pinning**, which allows them to **bypass third-party certificates**. As a result:

❌ You won’t be able to see the request even if capturing is on.  
💡 The connection will appear encrypted or not show up at all.

---

## 🛠️ Possible Fixes for Certificate Pinning  

1. 🔙 **Use Older Versions** of the app (before pinning was introduced).  
2. ⚙️ Use tools like **Frida**, **Xposed**, or **Magisk Modules** for advanced bypass (Rooted devices).  
3. ⛔ Disable SSL Pinning via decompilation (APKTool or JADX – advanced users only).  
4. 📱 Use emulators with modified environments for easier interception.

---

## 📊 How to Analyze Requests  

Once capturing is working, you’ll see:

| Term      | Meaning |
|-----------|--------|
| **Headers**  | Info like content type, user-agent, auth tokens |
| **Request**  | What your device is sending (GET, POST etc.) |
| **Response** | The data returned from the server (JSON, HTML etc.) |
| **Origin**   | The source of the request |
| **Referer**  | Previous page or link that led to this request |

You can right-click on requests in Fiddler or Reqable to **copy links, inspect bodies**, and more.

---

## 📺 Android TV and Other Devices  

To intercept traffic from devices **other than your phone/PC**, do this:

1. Connect the target device to the **same Wi-Fi/hotspot** as your phone/laptop running Reqable or Fiddler.
2. Go to the **proxy settings** on the target device.
3. Set the proxy to:
   - **IP Address** = Your capturing device’s **local IPv4**  
   - **Port** = The port used by Reqable/Fiddler (default: 8888)

> You can find your local IP using `ipconfig` on Windows or inside Reqable app.

---

## 🔗 Extracting M3U and Other Links  

Many streaming apps send **.m3u or .m3u8** playlist links as part of their media playback:

1. Filter for requests with `.m3u` or `.m3u8`.  
2. Copy the URL and test it in a player like **VLC** or **MX Player**.  
3. You can save or use these links as you wish (within legal bounds ⚖️).

---

## 📚 Glossary of Headers  

| Header | Meaning |
|--------|---------|
| **User-Agent** | Info about device/app making the request |
| **Content-Type** | Type of data sent (e.g., application/json) |
| **Authorization** | Token or credentials used |
| **Host** | The server being accessed |
| **Accept** | Expected response format |
| **Referer** | Previous request location |
| **Origin** | Where the request originated |

---

## 📌 Final Thoughts  

This guide should help you get started with intercepting and understanding your device’s network behavior.

🔐 Always remember that **ethical use** of these tools is key.  
Only inspect your own devices or apps you have permission to analyze.  

Use it for learning, security research, or debugging—**never for harmful intent**.

---

## ⚠️ Disclaimer  

> This guide is for **educational purposes only**.  
Using these tools on unauthorized apps or devices may violate terms of service or laws in your region. Proceed responsibly.

---

## 🧑‍💻 Author  

Made with ❤️ by **Techie**  
📫 Stay curious. Keep tinkering.  
📘 Follow me on GitHub!
