## 📱 Android Setup 

### Step 1: Install Termux
Download and install the **Termux** app (a terminal emulator for Android). It is highly recommended to download it from [F-Droid](https://f-droid.org/packages/com.termux/), as the Google Play Store version is outdated.

### Step 2: Install zrok
Open the Termux app. Copy the following block of commands, paste it into Termux, and press Enter. This will update your packages, download the tool, and extract it.

```bash
pkg update -y
pkg install wget tar -y
wget [https://github.com/openziti/zrok/releases/download/v2.0.1/zrok_linux_arm64.tar.gz](https://github.com/openziti/zrok/releases/download/v2.0.1/zrok_linux_arm64.tar.gz)
tar -xvf zrok_linux_arm64.tar.gz
chmod +x zrok
```

### Step 3: Authenticate & Open the Tunnel
Now, authenticate your phone and open the bridge to the server. Run these two commands one by one:

**1. Authenticate your device:**
```bash
./zrok enable [TEXT ME FOR THE ACCOUNT TOKEN]
```

**2. Start the tunnel:**
```bash
./zrok access private [TEXT ME FOR THE SHARE TOKEN] --bind 127.0.0.1:25565
```
*(Keep the Termux app open and running in the background!)*

### Step 4: Connect in Minecraft
1. Open your **Minecraft** app.
2. Go to the servers tab and tap **Add Server**.
3. Set the **Server Address** to `127.0.0.1` and the **Port** to `25565`.
4. Save and join the server!
