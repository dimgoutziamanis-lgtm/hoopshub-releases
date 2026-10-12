# Installing HoopsHub on an iPhone with SideStore (free)

HoopsHub isn't on the App Store. This guide installs it for free with
[SideStore](https://sidestore.io), which signs apps with a normal Apple ID and
renews them on the iPhone itself. You only need a Windows PC once, for setup.

> Apps signed with a free Apple ID last 7 days. SideStore renews them over
> Wi-Fi, so HoopsHub keeps working as long as it is refreshed at least once a
> week. If it expires, your data stays on the phone and a refresh brings the
> app back.

## What you need

- An iPhone on iOS 15 or later, **with a passcode set**
- A Windows 10/11 PC (64-bit; Windows on Arm isn't supported) and a USB cable
- An Apple ID. Use the iPhone owner's own Apple ID, since it gets signed into
  SideStore on that phone. A spare Apple ID works too.
- Wi-Fi. Refreshing doesn't work over mobile data.
- `HoopsHub.ipa`, from the [latest release](https://github.com/dimgoutziamanis-lgtm/hoopshub-releases/releases/latest)

## 1. Prepare the iPhone

1. Install **LocalDevVPN** from the App Store.
2. Open it and tap **Connect**. Tap **Allow** and enter the passcode when iOS
   asks to add the VPN configuration.

SideStore needs LocalDevVPN switched on whenever it installs or refreshes
apps. It doesn't send your traffic anywhere; it only lets SideStore talk to
the phone itself.

## 2. Prepare the PC

1. Install **iTunes** from Apple's website (the direct download, not the
   Microsoft Store version). If that doesn't work, try the **Apple Devices** app.
2. Download and install **iloader** (`.msi` recommended) from
   <https://github.com/nab138/iloader/releases>.

## 3. Install SideStore with iloader

1. Plug the iPhone into the PC. On the phone, tap **Trust** and enter the
   passcode.
2. Open **iloader** and sign in with the Apple ID.
3. Select the iPhone, then click **Install SideStore (Stable)**. It takes a
   few minutes.

## 4. Finish setup on the iPhone

1. **Trust the developer:** Settings → General → VPN & Device Management →
   under *Developer App* tap the Apple ID → **Trust**.
2. **Turn on Developer Mode:** Settings → Privacy & Security → scroll to the
   bottom → **Developer Mode** on. The phone restarts; confirm after reboot.
3. Open **LocalDevVPN** and tap **Connect**.
4. Open **SideStore** and sign in with the same Apple ID used in iloader.
5. Go to **My Apps** and tap the **7 DAYS** button next to SideStore to finish
   setup. If asked to revoke or create a certificate, tap **Yes**.

The PC is no longer needed after this.

## 5. Install HoopsHub

1. Get `HoopsHub.ipa` onto the iPhone's **Files** app, for example through
   iCloud Drive, OneDrive or Google Drive, or as an email attachment saved
   to Files.
2. With LocalDevVPN connected, open SideStore → **My Apps** → tap **+** →
   pick `HoopsHub.ipa`.
3. HoopsHub appears on the home screen. On first launch, allow camera access
   so the shot counter can work.

## 6. Keeping it working

- **Refresh at least once every 7 days:** connect LocalDevVPN, open SideStore,
  and tap **Refresh All** in My Apps.
- **Automate it (optional):** in the Shortcuts app, create a personal
  automation (e.g. daily at a set time, or when connecting to home Wi-Fi) that
  connects LocalDevVPN and runs SideStore's **Refresh All** action.
- **Updating HoopsHub:** install the new `HoopsHub.ipa` through SideStore the
  same way. It replaces the old version and keeps your data.
- A free Apple ID allows **3 sideloaded apps** at once, and SideStore counts as
  one of them.

## Troubleshooting

- **Install or refresh fails:** make sure LocalDevVPN is connected and the
  phone is on Wi-Fi, then try again.
- **"Pairing file" errors:** the pairing file can expire after an iOS update
  or reset. Plug the phone into the PC, open iloader and use its option to
  replace the pairing file.
- **HoopsHub won't open:** it expired. Connect LocalDevVPN and refresh it
  in SideStore.
- More help: [SideStore troubleshooting](https://docs.sidestore.io/docs/troubleshooting/common-issues)
  and [FAQ](https://docs.sidestore.io/docs/faq).
