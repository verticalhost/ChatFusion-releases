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

ChatFusion merges the live chat of eleven streaming platforms into a single stream
of messages. You add the platforms you stream on, type your channel names, and you
get one chat in the app window, chat overlays for OBS, a viewer counter, and alert
cards for follows, subscriptions, gifts, donations and raids.

Reading is anonymous everywhere: no account, no API key, no token. Every connector
uses the public read access each platform already offers to its own web page.

This repository hosts the Windows installers and the update metadata. The source
code is maintained privately.

## A quick tour

### One chat from every platform

<p align="center">
  <img src="misc/screenshots/window.png" alt="ChatFusion merging chat from Twitch, YouTube, Kick, VPZONE and WorldsWave" width="900">
</p>

Every message lands in one list, in the order it was written, with the platform's
logo in front, the author's colour, and their badges (SUB, MOD, VIP). Emotes and
emoji show as images. Alerts appear right in the chat as a highlighted line, so a
new subscriber or a raid never scrolls past unnoticed. The top bar adds up the
viewers of every platform, and each channel shows its own count and a green lamp
while it is connected.

### Only the platforms you use

<p align="center">
  <img src="misc/screenshots/add-platform.png" alt="The Add a platform list, filtered by a search" width="900">
</p>

The channel list stays short: it only shows the platforms you stream on. **Add a
platform** opens a list with a search field; pick one, type your channel name, and
it is added. Hover a row and click the cross to remove it.

### Start, stream, stop

<p align="center">
  <img src="misc/screenshots/window-folded.png" alt="The channel panel folded away, leaving the chat the whole window" width="900">
</p>

ChatFusion opens stopped, so nothing connects until you are ready. Press **Start**:
every platform connects and the channel panel folds away, leaving a slim rail of
lamps and the chat the whole window. Press **Stop** and every platform drops at
once, while the messages already on screen stay there to read.

### Alert cards in OBS

<p align="center">
  <img src="misc/screenshots/obs-scene.jpg" alt="An alert card over a game in OBS" width="900">
</p>

**Copy alerts** gives you one transparent page for OBS. Follows, subscriptions,
gifted subs, donations and raids from every platform arrive as cards, one after the
other, each with the platform's logo, the name, the amount and any message. A thin
bar empties while the card is on screen, so viewers know how long it stays. Place
and resize the source in OBS like any other.

<p align="center">
  <img src="misc/screenshots/alert-styles.jpg" alt="The five alert card styles: Subtle, Glass, Neon, Pill and Big" width="900">
</p>

Five card styles, from a quiet dark card to a big centred one for the moments that
deserve it.

### Customize once, for every platform

<p align="center">
  <img src="misc/screenshots/customize.png" alt="The Alerts window: card style, live preview, sound and which alerts to show" width="900">
</p>

**Customize** opens one small window, and whatever you pick applies to every
platform, so five platforms take no longer to set up than one:

- **Card style**: A to E, with a live preview that plays through a sub, a gift, a
  donation and a raid.
- **Sound**: Chime, Pop or Fanfare, or **My sound** to use your own MP3, WAV or OGG
  file. Click a sound to hear it.
- **Alerts to show**: a switch each for follows, subscriptions, donations and gifts,
  and raids.
- **Test an alert**: a sample card appears in OBS straight away, so you can check the
  style and the sound on your actual scene.

### Dark or light

<p align="center">
  <img src="misc/screenshots/window-light.png" alt="ChatFusion in the light theme" width="900">
</p>

Dark by default, light in one click, and the Windows title bar follows.

### Set up OBS in three steps

1. In ChatFusion, add your platforms and press **Start**.
2. Click **Copy chat**, **Copy alerts** or **Copy viewer count** at the bottom of the
   window.
3. In OBS, add a **Browser** source, paste the address as its URL, and place it on
   your scene. A size of 800 × 600 suits the chat and the alerts.

*The screenshots use made-up channels and messages.*

## Download and install

Pick the file for your system on the
[releases](https://github.com/verticalhost/ChatFusion-releases/releases) page:

| System | File | Then |
| --- | --- | --- |
| Windows 10 and 11 | `ChatFusion-Setup-x.y.z.exe` | Run it. The installer is per user and needs no administrator rights. |
| Linux, any distribution | `ChatFusion-x.y.z-x86_64.AppImage` | Make it executable (`chmod +x`) and run it. No installation. |
| Debian, Ubuntu, Mint | `ChatFusion-x.y.z-amd64.deb` | Install it with `sudo apt install ./ChatFusion-x.y.z-amd64.deb`. |

Then add your platforms, type your channel names, press **Start**, and paste the OBS
links into a browser source. The app opens stopped: nothing connects until you press
Start, and Stop drops every platform at once.

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
| Velora | yes | no | yes |
| Pilled | yes | stickers | yes |
| Blaze | yes | yes | yes |
| Beam | yes | yes | yes |
| WorldsWave | yes | emoji | yes |

Beam relays other platforms into its own room. If you enable Beam together with a
platform it already carries, every message and every alert shows twice.

## Alerts by platform

Platforms don't all share the same events, so an alert only appears where the
platform actually sends it to a viewer without an account.

| Platform | Follows | Subscriptions | Gifted subs and gifts | Donations | Raids |
| --- | --- | --- | --- | --- | --- |
| Twitch | — | yes | yes | Bits, charity | yes |
| YouTube Live | — | memberships | gifted memberships, Jewels | Super Chat, Super Sticker, YouTube Giving | yes |
| Kick | — | yes | yes | Kicks | yes (hosts) |
| Rumble | — | — | gifted subs | Rants | yes |
| VPZONE | yes | yes | yes | Pixels | yes |
| SharePlay | yes | yes | gifted subs, coin gifts | — | yes |
| Velora | yes | yes | yes | Volts | yes |
| Pilled | — | yes | gifts, gifted subs | Goldpills | yes |
| Blaze | yes | yes | gifts | thanks, votes | yes |
| Beam | yes | yes | yes | Embers, tips | yes |
| WorldsWave | yes | — | gifts | tips | — |

A dash means the platform does not give that event to an anonymous viewer:
- Follows on Twitch, Kick and Rumble need the streamer's own login, and YouTube
  never sends new subscribers to the live chat.
- SharePlay tips need a login too.
- Alerts replayed from a platform's history when you press Start are not shown
  again; only what happens live becomes an alert.

## Features

- **One window, every chat.** Platform badge, author colour, role badges, emotes
  and animated GIFs, all merged in the order they arrive.
- **OBS overlays.** A chat overlay and a viewer counter, served as local pages you
  paste straight into a browser source. A copy button for each.
- **Messages that fade.** Set a delay and the overlay drops old messages, while the
  app window keeps the whole history to scroll back through.
- **Alert cards.** One OBS page for follows, subscriptions, gifts, donations and
  raids from every platform, shown one after the other with the platform's logo.
  Five card styles, picked once in Customize and applied to every platform, with a
  switch per kind of alert and a test button to see the card in OBS. Three alert
  sounds to pick from (chime, pop, fanfare), or your own MP3, WAV or OGG file.
- **Sound alert.** A sound on each new message and each alert card, following the
  window's Sound switch and volume. The history replayed on connect stays silent.
- **Only your platforms.** The channel list shows the platforms you use; the others
  wait behind Add a platform, with a search field.
- **Dark and light themes.** Dark by default, light in one click.
- **Chat window.** The overlay in its own window, optionally always on top.
- **System tray.** Closing the window keeps the chat running in the background.
- **Two languages.** French and English, following the language of the computer,
  with a manual override.

## OBS

These pages are served on the port shown in the window, 8357 by default.

| Page | Address |
| --- | --- |
| Chat | `http://localhost:8357/index.html?widget=messages` |
| Horizontal chat | `http://localhost:8357/horizontal.html` |
| Viewer counter | `http://localhost:8357/index.html?widget=states` |
| Alert cards | `http://localhost:8357/alert-cards.html` |

Paste one into an OBS browser source. The copy buttons at the bottom of the window
put them on your clipboard. The alert cards page is transparent: place and resize
the source in OBS, and pick the card style in the window under Customize. The
older sound-only page, `alerts.html`, is still served for existing scenes.


## Show it in Discord

Discord can tell your friends you are running ChatFusion while you stream.
Nothing needs setting up in the program: this is Discord's own detection of
what is running. In Discord, open Settings, find Registered Games under the
activity settings, choose **Add it!** and pick ChatFusion from the list of
running programs. Your activity then reads *Playing ChatFusion*.

## How it works

A small local server merges every connector into one stream and publishes it over
a WebSocket. The window and the OBS pages are both clients of that server, which
is why they always show the same chat.

Each connector turns its platform's own format into a shared message model: an
author with a colour, an avatar and role badges, then a list of contents that are
text, images, emotes or links.

## Troubleshooting

- **The window says the port is already in use.** Another program listens on
  8357. Change the port in the window; the OBS links follow the new port.
- **A platform stays on "connecting".** Check the channel name: Twitch and
  SharePlay want the channel name, YouTube wants a handle or channel ID, Rumble
  wants the video page name, the others want the channel slug from the address
  bar.
- **The chat is empty.** Check that you pressed *Start*. Messages appear as
  viewers write them; use the *Test* button to check the sound.
- **No alert shows in OBS.** Alerts only come from live events, and not every
  platform sends every kind (see the table above). Open Customize and press
  *Test an alert*: the card appears in OBS if the page is set up.

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
