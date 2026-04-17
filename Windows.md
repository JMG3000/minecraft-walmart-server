## 🎮 Windows

## Step 1: Open PowerShell
Press the **Windows Key**, type `PowerShell`, and hit **Enter**.

## Step 2: Install Dependencies & Download Tools
Copy the following block of commands, paste it into PowerShell, and press Enter. This will create a dedicated folder, install `wget`, and download/extract the required tunnel tool.

```powershell
# 1. Install wget via Windows Package Manager
winget install GNU.Wget --silent

# 2. Create a clean directory for the tunnel tools
mkdir C:\MinecraftTunnel
cd C:\MinecraftTunnel

# 3. Download the zrok executable

[Choose your platform](https://netfoundry.io/docs/zrok/how-tos/install)
here We are not tested on Ios, Mac, or Linux as of now!

curl.exe -L "https://github.com/openziti/zrok/releases/download/v2.0.1/zrok_2.0.1_windows_amd64.tar.gz" -o zrok.tar.gz

# 4. Extract the executable
tar.exe -xf zrok2.tar.gz
```

## Step 3: Authenticate & Open the Tunnel
Once the files are extracted, you need to authenticate your device and open the bridge to the server. Run these two commands one by one.

**1. Authenticate your device:**
```powershell
.\zrok2.exe enable [TEXT ME FOR THE ACCOUNT TOKEN]
```

**2. Start the tunnel:**
```powershell
.\zrok2.exe access private [TEXT ME FOR THE SHARE TOKEN] --bind 127.0.0.1:25565
```
*(Keep this PowerShell window open and running in the background while you play!)*

## Step 4: Connect in Minecraft
With the tunnel running in the background, you can now launch the game.

1. Open **Minecraft: Java Edition**.
2. Go to **Multiplayer** > **Direct Connection**.
3. Enter the following Server Address exactly: `127.0.0.1:25565`
4. Click **Join Server**.
