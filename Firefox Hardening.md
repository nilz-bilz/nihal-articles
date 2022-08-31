# Firefox Hardening Guide

![ffboxer](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.ytimg.com%2Fvi%2FDovVeT1N_rQ%2Fmaxresdefault.jpg&f=1&nofb=1)
----------------------------------
## Why Harden Firefox?
Even though Firefox has the POTENTIAL to be much better for your privacy than Google Chrome, it’s not great out-of-the-box. By default, Firefox collects data via telemetry and crash reporting, and many privacy-enhancing features aren’t enabled by default. By hardening Firefox, telemetry and crash reporting can be disabled, and online tracking can be mostly prevented. This way, there is much less chance for most websites to track you.
<!--more-->

If you are looking for a pre-hardened version of firefox, check out [Librewolf](https://librewolf.net/). This option is quite hardened by default and can be a little overkill for many. In that case you might prefer to customize it on your own and find your own convenience/security tradeoff. 

## [A] **Basic Settings:**
To open the Firefox Preferences menu, open menu (top-right of browser window) and click **“Preferences.”**
Alternatively, enter <code>about:preferences</code> in the url box
#### 1. Under the "General" tab:

- **untick** recommend extensions as you browse
- **untick** recommend features as you browse
- Go to "Network Settings" & **tick** "Enable DNS over HTTPS" (ONLY if you DON'T use a VPN)

#### 2. Under the "Home" tab *untick*:

- Web Search
- Shortcuts (or at least sponsored shortcuts)
- Recent activity

#### 3. Under the "Search" tab:

- Change default search engine to "DuckDuckGo"
- **untick** ALL boxes under "Search Suggestions"
- remove "bing", "amazon", etc from "search shortcuts"

#### 4. Under the "Privacy & Security" tab:

- Choose **"Custom"** under "Enhanced Tracking Protection"
    - Under "Cookie" select **"All third-party cookies"**
    - Under "Tracking content" select **"In all windows"**
- Under "Send websites a 'Do Not Track' signal" select **"Always"**
- Under "Cookies and Site Data", it is advisable to **tick** *"Delete cookies and site data when Firefox is closed"* ... and add all the sites you would like to stay logged in with by adding their URL's into the "Manage Exceptions" box. However if you find this option too tedious and do not have a high ["threat model"](https://owasp.org/www-community/Threat_Modeling) then you may skip this. 
- Under "Logins and Passwords" **untick** ALL boxes. Use a ["Password Manager"](https://write.as/nihal-atwal/online-security-essentials-part-1-2-password-managers) instead.
- Under "History" select "Use custom settings", & tick **"Clear history when Firefox closes"**
- Under "Permissions" click on the "settings..." button for each permission and **tick** the "block new requests..." box and click "save changes". Do not do this for camera and microphone if you intend to use this browser for calls. (For autoplay select "Block Audio & Video")

Important: 

- Under "Firefox Data Collection and Use" **untick** ALL boxes
- Under "HTTPS-Only Mode" select **"Enable HTTPS-Only Mode in all windows"**
- Under "Security" you can *untick* all boxes under "Deceptive Content and Dangerous Software Protection" IF you want to stay private from Google (since this feature uses Google services), but if you don't particularly care about that and are more focused on SECURITY ONLY then leave them as is.

## [B] Advanced Configuration
The true hardening starts here. First steps will disable telemetry, then the rest will be split into levels L1, L2, L3, where L1 items are recommended for everyone, L2 items may cause minor inconveniences (in exchange for better privacy and security), L3 items are intended for advanced users.

To access these advanced settings, enter <code>about:config</code> into the address bar and hit enter. When you see a warning screen, click **I accept the risk** to continue.

All configuration items are in alphabetical order, and easily searchable using the search bar on the top of the page. 

Double-click on a configuration item/flag to modify it. 

### Disable Telemetry
<code>browser.newtabpage.activity-stream.feeds.telemetry</code> = false
<code>browser.ping-centre.telemetry</code> = false
<code>browser.tabs.crashReporting.sendReport</code> = false
<code>toolkit.telemetry.server</code> delete URL and leave it empty
<code>toolkit.telemetry.unified</code> = false

### [L1]

<code>beacon.enabled</code> = false
<code>geo.enabled</code> = false
<code>dom.battery.enabled</code> = false
<code>network.dns.disablePrefetch</code> = true
<code>network.prefetch-next</code> = false
<code>privacy.firstparty.isolate</code> = true
<code>privacy.trackingprotection.enabled</code> = true
<code>extensions.pocket.enabled</code> = false
<code>pdfjs.enableScripting</code> = false
<code>identity.fxaccounts.enabled</code> = false
<code>browser.preferences.moreFromMozilla</code> = false
<code>dom.webnotifications.enabled</code> = false

### [L2]
<code>privacy.resistFingerprinting</code> = true (this may break certain elements of a small number of sites)
<code>network.http.sendRefererHeader</code> = 0 (this may not let you load certain forums, in which case switch it back to default temporarily)
<code>security.ssl.require_safe_negotiation</code> = true (A small number of sites with outdated less secure legacy SSL/TLS might no longer work after changing this option. If you find this to be an issue revert it to default)
<code>webgl.disabled</code> =  true (This will break any website that depends on WebGL graphics)

### [L3]
<code>media.eme.enabled</code> = false
<code>media.navigator.enabled</code> = false
<code>media.peerconnection.enabled</code> = false
(The above flags will disable WebRTC which is used by video conferencing services in browsers. Those sites will cease to function)
<code>dom.event.clipboardevents.enabled</code> = false (tends to break Google Docs and similar sites)
<code>privacy.resistFingerprinting.letterboxing</code> = true (creates a border around the screen for hiding the device's true resolution)
<code>network.captive-portal-service.enabled</code> = false (disables the ability to sign in to public wifi networks)
<code>dom.webaudio.enabled</code> = false (disables all audio)

## [C] Install Addons
These must have add-ons require minimal configuration and can dramatically improve the security and privacy in Firefox.

1. **[uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)**: This is most powerful open-source ad and tracker blocker. It can block ads, trackers, malwares, annoyances, and more. It also significantly improves page load speed.
If you want to customize it, please refer to the [official wiki](https://github.com/gorhill/uBlock/wiki).

2. **[Facebook Container](https://addons.mozilla.org/en-US/firefox/addon/facebook-container/)**: If you use Facebook services (such as FB, Instagram, etc), this addon will open all those sites in a separate "container" tab that keep away all browser cookies and trackers away from other parts of the browser. 

This also enables the "container tab" feature in Firefox where you can create multiple container profiles for different kinds of accounts and keep all their browsing data separate. This is accessible by right-clicking on the new tab button. "Manage Containers" will let you edit them. This greatly improves Privacy & Security. 

```Nihal Atwal 2022``` [*PGP Public Key*](https://write.as/g7kpl5o65j0l8gkk.md)