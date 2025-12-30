# 🕵️‍♂️ TotalOSINT

**The All-in-One, Client-Side OSINT Investigation Tool.**

TotalOSINT is a privacy-first, client-side OSINT toolkit for security analysts. Instantly extract IOCs (IPs, Domains, Hashes) from raw logs and launch bulk investigations across dozens of threat intelligence sources. Zero-data-persistence workflow for SOC and DFIR teams. No installation required.

[![Live Demo](https://img.shields.io/badge/demo-Live%20on%20GitHub%20Pages-brightgreen?style=for-the-badge&logo=github)](https://jhatzimalis.github.io/TotalOSINT)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Security](https://img.shields.io/badge/Security-Client%20Side%20Only-green.svg)


https://github.com/user-attachments/assets/36fe62e4-7047-4f83-8eb0-c3ec89e52ed2


## ✨ Features

* **⚡ Smart Extraction:** Automatically detects and sorts IPv4/IPv6, Domains, URLs, and MD5/SHA Hashes from raw text.
* **🛡️ OPSEC First:** Zero data persistence. Inputs and investigation notes are held in RAM only and wiped on page refresh. No data is sent to any backend server.
* **🚀 Bulk Investigation:** Select multiple sources and open them all in new tabs with one click.
* **📂 Case Management:** Triage entities (Safe, Suspicious, Malicious) and generate formatted text reports for your case files.
* **🔖 Bookmarks:** A dedicated dashboard for quick access to your favorite tools.
* **⚙️ Customizable:** Add your own custom internal or external sources directly via the settings.

## 📊 Supported Indicators

| Indicator | Support | Example |
| :--- | :--- | :--- |
| **IPv4 / IPv6** | ✅ | `1.1.1.1`, `2606:4700...` |
| **Domains** | ✅ | `google.com` |
| **URLs** | ✅ | `hxxps://malicious-site.com/path` |
| **Hashes** | ✅ | MD5, SHA-1, SHA-256 |

## 🚀 Usage

### Option 1: GitHub Pages
Visit the live deployment via GitHub Pages. Link 🠊 [jhatzimalis.github.io/TotalOSINT](https://jhatzimalis.github.io/TotalOSINT)

### Option 2: Local / Offline
TotalOSINT is a static web application. You can run it entirely offline.
1.  Download `index.html` and `sources.js`.
2.  Open `index.html` in any modern web browser.

## 🛠️ Configuration

### Adding Custom Sources
You can add your own tools via the **Settings (⚙️)** menu. These are saved to your browser's local storage.
* **ID:** A unique identifier (e.g., `MY_TOOL`).
* **Lookup URL:** The URL used to search. Use the tool's search parameter format. TotalOSINT appends the entity to the end of this URL.
    * *Example:* `hxxps://example.com/search?q=`

### Advanced: `sources.js`
If you are self-hosting, you can modify the `sources.js` file to permanently change the default toolset.

```javascript
const sources = {
    ip: [
        { 
            id: 'TOOL_ID', 
            name: 'Tool Name', 
            url: 'hxxps://example.com', 
            lookupurl: 'hxxps://example.com/search/' // Optional
        }
    ],
    domain: [ ... ],
    hash: [ ... ],
    bookmarks: [ ... ]
};
```

## 🔒 Security & Privacy

* **Client-Side Execution:** All logic runs locally in your browser context. Data extraction (RegEx) occurs entirely on the client side.
* **No Tracking:** No analytics, no cookies, no external API calls.
* **Data Safety:** Raw inputs are **not** stored in LocalStorage. If your browser crashes or the tab is closed, the data is unrecoverable (fail-safe design).
* **Defanging:** Built-in "De-fang" toggle (`1[.]1[.]1[.]1`) prevents accidental clicks on malicious links in your reports.

## 🏷️ Tags

`osint` `threat-intelligence` `cybersecurity` `soc` `blue-team` `incident-response` `investigation` `ioc-extraction` `opsec` `malware-analysis` `security-tools` `infosec` `digital-forensics` `threat-hunting` `ioc-parser` `ioc-lookup` `reconnaissance` `client-side` `zero-persistence` `secops`

---

*Disclaimer: TotalOSINT is a tool for aggregation and workflow optimization. The author is not responsible for how the linked third-party services are used or the results they provide.*
