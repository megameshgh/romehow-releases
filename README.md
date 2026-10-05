# romehow

> [!CAUTION]
> Alpha for invited testers only. Do not install this unless you were invited
> and know what it is.
>
> Designed for laptop work with a touchpad and one screen. Mouse and multi-screen
> fallbacks are supported but untested.
>
> Primarily tested in dark mode. Light mode is available; romehow follows your
> Windows system theme.

Your keyboard control is powered by [Kanata][kanata-source], a powerful open-source
keyboard remapper written in Rust. Its layers, tap-hold keys and chords let you
shape your keyboard around how you work. Romehow runs the official, unmodified
release as a separate program through its public TCP interface.

<!-- BEGIN KANATA RELEASE -->
Bundled: [Kanata v1.12.0][kanata-source] (LGPL-3.0-only).
[Source archive][kanata-source-archive] | [License][kanata-license] |
[Third-party notices](THIRD-PARTY-NOTICES.txt).

[kanata-source]: https://github.com/jtroo/kanata/tree/v1.12.0
[kanata-source-archive]: https://github.com/jtroo/kanata/archive/refs/tags/v1.12.0.zip
[kanata-license]: https://github.com/jtroo/kanata/blob/v1.12.0/LICENSE
<!-- END KANATA RELEASE -->

## Install

- **Windows 11 x64:** download the `Setup.exe` asset from the latest
  [release](https://github.com/megameshgh/romehow-releases/releases) and run it.
  The alpha binaries are unsigned. Read `LICENSE.txt` before installing.
- **App files:** `%LOCALAPPDATA%\romehow-app\current`.
  You don't need to install [Kanata][kanata-source] separately.
- **Run at login:** fresh installs start when you sign in. Disable it in
  Windows Settings > Apps > Startup.
- **Uninstall:** remove romehow in Settings > Apps > Installed apps. This removes
  `romehow-app`, including its saved session. Your profiles in
  `%APPDATA%\romehow-profiles` stay untouched.

## Profiles

- **Works immediately:** romehow loads the bundled demo when you have no profiles.
- **Your files:** put your `.kbd` files in `%APPDATA%\romehow-profiles`.
  romehow creates the folder on first launch.
  Debug and Release use the same folder.
- **Multiple profiles:** top-level `.kbd` files load in filename order, ignoring
  case. Put include-only files in a subfolder so they aren't loaded as profiles.
- **One bridge:** `app.bridge.kbd` stays beside `romehow.exe`. In your custom
  profile, include its quoted absolute path, for example
  `(include "C:/Users/yourname/AppData/Local/romehow-app/current/app.bridge.kbd")`.
  Use your actual path. [Kanata][kanata-source] includes do not expand `~` or
  environment variables.
- **Customize the demo:** copy `app.demo.kbd` from beside the executable into your
  profiles folder as `00-main.kbd`, then change its include as described above.
- **Keep your files:** updates replace the app files, not your profiles. The
  profiles folder can be a junction to a local OneDrive, Dropbox or git folder.
  Keep synced files available offline. An inaccessible profiles folder reports
  an error rather than loading the demo.
