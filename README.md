# SingIt releases

Signed builds of the **SingIt** Chrome extension. Extension id: `chnemnegpcbkemaaekhkchgigbgdcaik`.

Chrome on macOS and Windows only installs extensions from outside the Chrome Web Store through a policy. Clicking the `.crx` in a release won't work. Install with the policy for your OS below. Chrome then downloads SingIt from this repo and **keeps it updated automatically** from the latest release.

## Install

### macOS

1. Download [`policy/singit-chrome.mobileconfig`](https://github.com/guypeled76/singit-releases/raw/main/policy/singit-chrome.mobileconfig) and double-click it.
2. Open **System Settings → General → Device Management** (called **Profiles** on older macOS), select **SingIt Chrome extension**, and click **Install**.
3. Quit Chrome completely (⌘Q) and reopen it.

### Windows

1. Download [`policy/singit-chrome.reg`](https://github.com/guypeled76/singit-releases/raw/main/policy/singit-chrome.reg).
2. Double-click it and accept the prompts (needs administrator rights).
3. Restart Chrome.

### Linux

```sh
sudo mkdir -p /etc/opt/chrome/policies/managed
sudo curl -L -o /etc/opt/chrome/policies/managed/singit-chrome.json \
  https://github.com/guypeled76/singit-releases/raw/main/policy/singit-chrome-linux.json
```

Restart Chrome.

### Check it worked

- `chrome://policy` lists **ExtensionInstallForcelist** with status OK (click **Reload policies** if not).
- `chrome://extensions` shows **SingIt**, installed by your organization. It can take a minute after Chrome starts.

## Using SingIt

Click the SingIt toolbar icon to open your library and sign in with Google (your account must be on the allowlist). On a song page from **Tab4U**, **Ultimate Guitar** or **Shironet** the icon shows a green **+**. Click it to import the song.

## Uninstall

- **macOS:** remove the **SingIt Chrome extension** profile in System Settings → General → Device Management.
- **Windows:** delete the value under `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome\ExtensionInstallForcelist` that mentions `chnemnegpcbkemaaekhkchgigbgdcaik`.
- **Linux:** `sudo rm /etc/opt/chrome/policies/managed/singit-chrome.json`

Restart Chrome afterwards.

## Release files

Each release holds the signed `.crx`, a `.zip` with the same files, and `update.xml`, the file Chrome checks for updates:
`https://github.com/guypeled76/singit-releases/releases/latest/download/update.xml`
