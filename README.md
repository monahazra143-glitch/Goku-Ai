# update.json kaise kaam karta hai

App **License page → Check for updates** dabane par neeche wali file padhta hai:

`https://raw.githubusercontent.com/monahazra143-glitch/Goku-Ai/main/update.json`

Ye file repo ke **main branch ke root** me hi rakhein, aur naam bilkul `update.json`.

## Fields

| Field | Matlab |
|---|---|
| `versionName` | Naya version, jaise `1.2.15`. App ke andar ke version se **bada** hona chahiye, tabhi update dikhta hai. |
| `versionCode` | Number, har release par badhta hai (`build.gradle.kts` wala). |
| `apkUrl` | APK ka seedha download link. |
| `notes` | Update ki poori details. Har line ke liye `\n` lagayein. App me card ke andar dikhti hai. |
| `force` | `true` ho to user ko update karna hi padega. Aam taur par `false`. |

## Naya version nikalne ke 6 kadam

1. `MainActivity.java` me `APP_VERSION` badlein.
2. `build.gradle.kts` me `versionName` aur `versionCode` (**badhao**) badlein.
3. APK banayein aur uska naam `Goku_<version>.apk` rakhein.
4. GitHub par naya **Release** banayein: tag `V<version>`, APK attach karein, Publish karein.
5. **Release ban jaane ke baad hi** `update.json` me `versionName`, `versionCode`, `apkUrl`, `notes` badal kar main branch me daalein.
6. Website (`index.html`) aur `README.md` me download link bhi nayi APK par badlein.

> Tag, APK ka naam, `apkUrl` aur `versionName` ek jaise honge to hi sab chalega. Galat link par app "Download fail" dikhayega.
