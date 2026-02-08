# Phira FAQ

This is the *Phira FAQ* written by Phira support volunteers. Before playing Phira, please read and agree to the official [Terms of Service](https://phira.moe/terms-of-use) and [Privacy Policy](https://phira.moe/privacy-policy).

v0.6.7.1 update highlights:

- Cache management in Settings
- Localization improvements
- RPE text support improvements
- Fixed black screen bug in some cases

For issues with this document, contact @Dmocken in the [Phira QQ Channel](https://pd.qq.com/s/ezgv3q71g), or use [Feedback](https://phira.dmocken.top/report).

## Before you start

1. A device to play on (Android 7+ for online services, iOS 12+ for Apple devices).
2. A personal email address.
3. Some basics: e.g. IPA is the iOS app package and needs signing; APK is the Android/Harmony app package (32-bit and 64-bit—choose according to your device), and where phone storage paths are.

## Android download

1. Official:
   - [GitHub](https://github.com/TeamFlos/phira/releases)
2. If you see "device not supported", "CPU incompatible", or install failure, try the **32-bit** build.
3. 64-bit works on most Android/Harmony devices. **There is no Harmony NEXT–specific sideload package.**

## iOS download

> [!NOTE]
> For iOS Recommended Trun To [App Store](https://apps.apple.com/us/app/phira/id6447435864) To Download

## FAQ

### [Terms of Service](https://phira.moe/terms-of-use) and [Privacy Policy](https://phira.moe/privacy-policy)

- You must read and agree to them; Phira may refuse service if you do not.
- After you read them, the popup will close, which means you have read and agreed.

### Account and password

- After registering, check your email for the verification message; check spam or refresh if it doesn’t arrive.
- If an invite link says "invalid activation code" within 10 minutes, it may be a bug; try logging in with your email and password in Phira.
- To reset password: [Reset password](https://phira.5wyxi.com/reset-password). Enter your email to receive a reset link. A blank screen after submitting is a known bug; if you don’t get the link within 5 minutes, try again.
::: warning
If the link in the email doesn’t open, replace `api.phira.cn` at the start of the URL with `phira.5wyxi.com`
:::

### Online services

- For chart load/download errors, check that your app version is the latest (0.6.7.1). If it is, the issue may be server-side or rate limiting; try again later.
- If scores don’t upload and you see "Uploading score", the server is having network issues; you can enable Offline mode if you don’t care about uploading.
- If charts fail to download (long error message) or download very slowly, try:
  - Wait about an hour and try again
  - Switch network (e.g. Wi‑Fi ↔ mobile data)
  - Enable "Insecure mode" in-game and restart
  - Turn on airplane mode or restart the device
  - Change carrier / use a proxy
  - Wait for server recovery

### Multiplayer

- Official Phira multiplayer server (mp2.phira.cn:12345) is currently unavailable.
- Third-party monitoring for multiplayer servers: [Status page](https://status.dmocken.top).
- We support and recommend self-hosted multiplayer servers: [phira-mp on GitHub](https://github.com/TeamFlos/phira-mp).
- Pre-built server files: [Multiplayer server](https://phira.dmocken.top/mulity).
- [Android: Phira multiplayer server (Termux)](/mp_build_guide/Termux)
- [Windows: Phira multiplayer server](/mp_build_guide/Windows)
- [Linux server deployment](/mp_build_guide/Linux)

### Touch / input issues

- iOS: Enable Guided Access.
- Android: Add the app to the system game space, or turn off multi-finger gestures and similar features.
- General: Turn off aggressive optimization / use low graphics; overheating can cause CPU throttling. Dirty screen can affect touch. If issues persist, check that the screen supports multi-touch.

### Resource packs

- Resource packs (skins and charts) are imported as zip files; do not unzip.
- Resource pack site: [prprBlog](https://prprblog.kevin2106.top/).
- QQ Channel: [Phira 资源包制作分享](https://pd.qq.com/s/blwfryimz).
- (Android) QQ file save path: `Android/data/com.tencent.mobileqq/Tencent/QQfile_recv`.
- Import on iOS: TestFlight builds can import; IPA (self-signed) builds often cannot import files (local chart import, resource pack import, avatar import may all fail).
- Resource pack import: Home → Resource pack → “+” on the left. Chart import: Play → “Import” (top right). Or choose “Phira (resource pack)” as the open-with app for the zip; if you see a purple title and white screen, try opening the zip from the file manager with “Phira (resource pack)”.

::: warning
The *Phigros Official Resource Pack* is © Pigeon Games. Phira does not have the right to distribute it; distribution has been stopped. Please do not share it without permission.
:::

### Custom charts

- To find charts for a specific song, searching on Bilibili and following the chart author’s download link is often fastest.
- Uploading: Before uploading, read and agree to [Phira chart upload notice](https://docs.qq.com/doc/DU2dUaEt5WnFJV2Zh) and [Phira chart content policy (chart creators)](https://docs.qq.com/doc/DU1dISHdEb0NuYVpB). **Phigros-exclusive tracks, original art, official charts, and official-chart derivatives are not allowed; violators may be banned.**
- For non-exclusive tracks, do not use original art; ensure your chart design differs from the official one. See the upload notice for more.
- On Windows and Linux, story charts and character art cannot be loaded for copyright reasons.

### Official contacts

- Discord: [Phira Official](https://discord.gg/9fH8UA9DgR)
- Telegram: [Phira](https://t.me/phira_official)
- QQ Channel: Phira
  - Invite: [https://pd.qq.com/s/ezgv3q71g](https://pd.qq.com/s/ezgv3q71g)
  - Channel ID: r48eajexth
- Bilibili: [Phira官方](https://space.bilibili.com/3493259571628094)
- Website: [https://phira.moe](https://phira.moe)
