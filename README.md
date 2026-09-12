<p align="center">
  <img src="assets/brand/logo-dark.svg#gh-dark-mode-only" alt="ChatFusion" width="260">
  <img src="assets/brand/logo-light.svg#gh-light-mode-only" alt="ChatFusion" width="260">
</p>

<p align="center">
  One chat from every platform you stream on, in a desktop app and in your OBS overlay.
</p>

<p align="center">
  <a href="https://github.com/verticalhost/ChatFusion-releases/releases/latest"><strong>Download the latest version</strong></a>
</p>

---

<p align="center">
  <img src="misc/screenshots/window.png" alt="The ChatFusion window" width="900">
</p>

ChatFusion merges the live chat of eight streaming platforms into a single stream
of messages. You type your channel name for each platform, and you get one chat in
the app window, one chat overlay for OBS, a viewer counter, and a sound alert.

Reading is anonymous everywhere: no account, no API key, no token. Every connector
uses the public read access each platform already offers to its own web page.

This repository hosts the Windows installers and the update metadata. The source
code is maintained privately.

## Download and install

Pick the file for your system on the
[releases](https://github.com/verticalhost/ChatFusion-releases/releases) page:

| System | File | Then |
| --- | --- | --- |
| Windows 10 and 11 | `ChatFusion-Setup-x.y.z.exe` | Run it. The installer is per user and needs no administrator rights. |
| Linux, any distribution | `ChatFusion-x.y.z-x86_64.AppImage` | Make it executable (`chmod +x`) and run it. No installation. |
| Debian, Ubuntu, Mint | `ChatFusion-x.y.z-amd64.deb` | Install it with `sudo apt install ./ChatFusion-x.y.z-amd64.deb`. |

Then type your channel names, click **Apply and connect**, and paste the OBS links
into a browser source.

Your channels are saved in your user profile, so an update or a reinstall does not
erase them.

Windows may show a SmartScreen notice the first time, because the installer is not
signed with a commercial certificate. Choose *More info*, then *Run anyway*.

On Linux, the AppImage needs FUSE 2 (`libfuse2`), which most distributions ship;
Ubuntu 22.04 and later may need `sudo apt install libfuse2`.

### Updates

The app updates itself on Windows and with the AppImage. It checks this repository
in the background, downloads a newer version quietly, and then shows a banner in the
window with a single **Restart and install** button. Nothing installs until you
click it. The .deb does not update itself: download the new package and install it
over the old one.

## Supported platforms

| Platform | Chat | Emotes | Viewers |
| --- | --- | --- | --- |
| Twitch | yes | native, plus BetterTTV, FrankerFaceZ and 7TV | yes |
| YouTube Live | yes | yes | yes |
| Kick | yes | yes | yes |
| Rumble | yes | yes | yes |
| VPZONE | yes | yes | yes |
| SharePlay | yes | yes | yes |
| Blaze | yes | yes | yes |
| Beam | yes | yes | yes |

Beam relays other platforms into its own room. If you enable Beam together with a
platform it already carries, every message shows twice.

## Features

- **One window, every chat.** Platform badge, author colour, role badges, emotes
  and animated GIFs, all merged in the order they arrive.
- **OBS overlays.** A chat overlay and a viewer counter, served as local pages you
  paste straight into a browser source. A copy button for each.
- **Messages that fade.** Set a delay and the overlay drops old messages, while the
  app window keeps the whole history to scroll back through.
- **Sound alert.** A sound on each new message, with volume and a minimum gap
  between two sounds. The history replayed on connect stays silent.
- **Chat window.** The overlay in its own window, optionally always on top.
- **System tray.** Closing the window keeps the chat running in the background.
- **Two languages.** French and English, following the language of the computer,
  with a manual override.

## OBS

Three pages are served on the port shown in the window, 8357 by default.

| Page | Address |
| --- | --- |
| Chat | `http://localhost:8357/index.html?widget=messages` |
| Viewer counter | `http://localhost:8357/index.html?widget=states` |
| Sound alert | `http://localhost:8357/alerts.html` |

Paste one into an OBS browser source. The copy buttons at the bottom of the window
put them on your clipboard.

The chat and viewer pages come from
[AxelChatWidgets](https://github.com/3dproger/AxelChatWidgets), which is under
AGPL-3.0 and is not part of ChatFusion. The installer ships it with its licence
notice. The sound alert page is part of ChatFusion.

## How it works

A small local server merges every connector into one stream and publishes it over
a WebSocket. The window and the OBS pages are both clients of that server, which
is why they always show the same chat.

Each connector turns its platform's own format into a shared message model: an
author with a colour, an avatar and role badges, then a list of contents that are
text, images, emotes or links.

## Troubleshooting

- **The window says the port is already in use.** Another program listens on
  8357. Change the port in the window and click *Apply and connect*; the OBS
  links follow the new port.
- **A platform stays on "connecting".** Check the channel name: Twitch and
  SharePlay want the channel name, YouTube wants a handle or channel ID, Rumble
  wants the video page name, the others want the channel slug from the address
  bar.
- **The chat is empty.** Messages appear as viewers write them. Use the *Test*
  button to send a sample message and check the sound and the overlay.

## Notes

Each platform is labelled with its own site icon, used only to say which service
a message came from. Those marks belong to their owners.

## Licence

Proprietary. All rights reserved. The source code is not open; the compiled
application is distributed for personal use.

---

<p align="center">
  Made by <a href="https://vpzone.tv"><strong>VPZONE.TV</strong></a>
</p>
