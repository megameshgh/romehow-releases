# romehow

> [!CAUTION]
> Alpha for invited testers only. Do not install this unless you were invited
> and know what it is.
>
> This software controls your keyboard and mouse. Bugs or faulty configurations
> can leave keys stuck or prevent normal input. You may need to restart Windows
> to regain control.

## Install

- **Windows 11 x64:** download the `Setup.exe` asset from the latest
  [release](https://github.com/megameshgh/romehow-releases/releases) and run it.
  The alpha binaries are unsigned. Read `LICENSE.txt` before installing.
- **App files:** installed in `%LOCALAPPDATA%\romehow-app\current`. Paste that
  path into File Explorer. You don't need to install Kanata separately.
- **Updates:** installed copies check at startup and every five minutes, then download in the
  background. Once an update is ready, holding the switcher shows a five-second
  countdown and relaunches romehow. Release to cancel the countdown. Your
  profiles and saved session stay intact. Map `@aupd` to check immediately.
  Enable the profiler with `@pfon` to see update status without holding the switcher.
- **Version:** hover over the tray icon to see your installed version.
- **Not at login yet:** running automatically at login comes later.
- **Uninstall:** remove romehow in Settings > Apps > Installed apps. This removes
  `romehow-app`, including its saved session. Your profiles stay untouched.

## Profiles

- **Works immediately:** romehow loads the bundled demo when you have no profiles.
- **Your files:** put your `.kbd` files in `%APPDATA%\romehow-profiles`. Paste that
  path into File Explorer to open it. romehow creates it empty on first launch.
  Debug and Release use the same folder.
- **Multiple profiles:** top-level `.kbd` files load in filename order, ignoring
  case. Put include-only files in a subfolder so they aren't loaded as profiles.
- **One bridge:** `app.bridge.kbd` stays beside `romehow.exe`. In your custom
  profile, include its quoted absolute path. For an installed copy, open the app
  files folder above and copy the full path of `app.bridge.kbd`, for example
  `(include "C:/Users/yourname/AppData/Local/romehow-app/current/app.bridge.kbd")`.
  Replace that example with your actual path. Kanata includes do not expand `~`
  or environment variables.
- **Customize the demo:** copy `app.demo.kbd` from beside the executable into your
  profiles folder as `00-main.kbd`, then change its include as described above.
- **Keep your files:** updates replace the app files, not your profiles. The
  profiles folder can be a junction to a local OneDrive, Dropbox or git folder.
  Keep synced files available offline. An inaccessible profiles folder reports
  an error rather than loading the demo.
