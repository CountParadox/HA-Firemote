# HA-Firemote
[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/PRProd/HA-Firemote?style=for-the-badge)
![Maintenance](https://img.shields.io/maintenance/yes/2023?style=for-the-badge)

Need More Information?  Check out this project's [Wiki](https://github.com/PRProd/HA-Firemote/wiki) page

| ![Fire TV Remote Style 6](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AF6.png) | ![Fire TV Remote Style 5](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AF5.png) | ![Fire TV Remote Style 4](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AF4.png) | ![Fire TV Remote Style 3](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AF3.png) | ![Fire TV Remote Style 2](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AF2.png)
| ------------- | ------------- | ------------- | ------------- | ------------- |

| ![Fire TV Remote Style 1](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AF1.png) | ![NVIDIA Shield Remote 2](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/NS2.png) | ![NVIDIA Shield Remote 1](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/NS1.png) | ![Xiaomi Mi Remote 2](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/XM2.png) |  ![Chromecast Remote](https://github.com/PRProd/HA-Firemote/assets/25486599/36a14224-b46f-4d4c-97ec-b1217e99b272)
| ------------- | ------------- | ------------- | ------------- | ------------- |

| ![App Launcher 1](https://github.com/PRProd/HA-Firemote/raw/main/Example%20Images/AL1.png) | ![App Launcher 2](https://github.com/PRProd/HA-Firemote/assets/25486599/9531fd5f-9003-41f1-bc05-a6d3962e346b)
| ------------- | ------------- |

<br>
<br>
<br>

## Prerequisites
* A functioning version of [Home Assistant](https://www.home-assistant.io/)
* [HACS](https://peyanski.com/how-to-install-home-assistant-community-store-hacs/) (not required, but it makes things easier)
* A supported device
  * Amazon Fire Smart TV
  * Amazon Fire Stick
  * Amazon Fire Cube
  * NVIDIA Shield
  * NVIDIA Shield Pro
  * Xiaomi Mi Box S
  * Chromecast
  * Other Android-based non-fire devices might work as well, but with limited (and unsupported) functionality

[Which Amazon Fire devices are supported?](../../wiki/Existing-Amazon-Devices---Support-Chart)<br>
[Which Amazon Fire device do I own?](https://developer.amazon.com/docs/fire-tv/device-specifications.html)<br>
[Which NVIDIA Shield devices are supported?](../../wiki/Existing-NVIDIA-Shield-Devices-Support-Chart)<br>
[Which NVIDIA Shield device do I own?](https://www.nvidia.com/en-us/shield/)<br>
Which Xiaomi Mi device do I own?<br>
Which Chromecast device do I own?

<br>
<br>
<br>

## Download and Setup via Home Assistant UI & HACS
1. [Turn on ADB Debugging](https://www.youtube.com/watch?v=40iVXrTWcPU) on your Amazon, Shield, Xiaomi, Chromecast, or Android TV device
1. Set up the Home Assistant [Android Debug Bridge Integration](https://www.home-assistant.io/integrations/androidtv/) and connect it to your device (**always required in every setup**)
1. Optionally, for non Amazon Fire devices only, you may additionally choose to set up the Home Assistant [Android TV Remote Integration](https://www.home-assistant.io/integrations/androidtv_remote/) and connect it to your device. (optional)
1. Click on HACS and select Frontend
1. In the lower right-hand corner, click the "+ EXPLORE & DOWNLOAD REPOSITORIES" button
1. Search for, and click on "Firemote Card" then click the "DOWNLOAD" button in the lower right-hand corner
1. You will be prompted to reload your browser.  Click the RELOAD button to continue

## OR Install Manually
1. [Turn on ADB Debugging](https://www.youtube.com/watch?v=40iVXrTWcPU) on your Amazon device
1. Set up the Home Assistant [Android Debug Bridge Integration](https://www.home-assistant.io/integrations/androidtv/) and connect it to your device (**always required in every setup**)
1. Optionally, for non Amazon Fire devices only, you may additionally choose to set up the Home Assistant [Android TV Remote Integration](https://www.home-assistant.io/integrations/androidtv_remote/) and connect it to your device. (optional)
1. Download the contents of the [dist/](https://github.com/PRProd/HA-Firemote/blob/main/dist/) directory, and place it in your Home Assistant /config/www directory
1. [Register the HA-Firemote.js file that you just installed as a new resource](https://developers.home-assistant.io/docs/frontend/custom-ui/registering-resources/)

<br>
<br>

## How to use
1. On any dashboard, click the +ADD CARD button
1. Search by cards for "Firemote Card" and click on it
1. Under the Android Debug Bridge Entity dropdown, a list of your Android Debug Bridge integration entities will appear.  Select the one you wish to control.
1. Under Device Family, choose "Amazon Fire", "Chromecast", "NVIDIA Shield", or "Xiaomi"
1. Under Device Type, select the device model that you own. (Which [Amazon Fire](https://developer.amazon.com/docs/fire-tv/device-specifications.html) or [NVIDIA Shield](https://www.nvidia.com/en-us/shield/)  device do I own?)
1. If you are setting up something other than an Amazon Fire device, select the Associated Android TV Remote Entity that points to the same device as your Android Debug Bridge entity.  This step is not required, but it will greatly improve the speed and reliability of your Firemote card
1. Make any other optional changes to your card, then click "SAVE"  Other options include changing the app launch buttons to apps that you use most often, or changing the style of your remote control to look like something completely different from what shipped with your device.  You can even add names and adjust the size of your Firemote card too!

![UIConfig](https://github.com/PRProd/HA-Firemote/assets/25486599/2fccafde-0267-4226-9775-ff803c5ecb86)

<br>
<br>
<br>

## Screenshots from Users
![Dashboard](https://github.com/PRProd/HA-Firemote/assets/25486599/ddc0dc74-2b5d-47bd-b73f-05249dda3377)<br>
[Click here](https://github.com/PRProd/HA-Firemote/discussions/129) to see the full gallery

<br>
<br>
<br>

## YAML card setup options
Examples:
```yaml
type: custom:firemote-card
entity: media_player.fire_tv_192_168_1_30
device_family: amazon-fire
device_type: fire_tv_4_series
compatibility_mode: default
app_launch_1: prime-video
app_launch_2: netflix
app_launch_3: hdmi_1
app_launch_4: youtube
hdmi_1: Cable
scale: 85
button_overrides:
  mute-button:
    script: receiver_mute_script
```
```yaml
type: custom:firemote-card
entity: media_player.android_tv_192_168_107_209
device_family: nvidia-shield
device_type: shield-tv-pro-2019
compatibility_mode: default
android_tv_remote_entity: remote.shield
scale: '100'
app_launch_1: netflix
app_launch_2: function-find-my-remote
app_launch_3: function-mute
```

Options:
| Name                   | Type   | Required | Options                                                          | Description                            |
| ---------------------- | ------ | -------- | ---------------------------------------------------------------- | -------------------------------------- |
| type                   | string | yes      | custom:firemote-card                                             | Type of the card                       |
| entity                 | string | yes      | any valid entity created in the [Android Debug Bridge Integration](https://www.home-assistant.io/integrations/androidtv/) | entity_id                              |
| device_family          | string | yes      | amazon-fire<br>chromecast<br>nvidia-shield<br>xiaomi             | Manufacturer Family                    |
|android_tv_remote_entity| string | no       | any valid entity created in the [Android TV Remote Integration](https://www.home-assistant.io/integrations/androidtv_remote/) | entity_id
| device_type            | string | yes      | chromecast-4k<br>[fire_tv_toshiba_v35](https://github.com/PRProd/HA-Firemote/wiki/Smart-TV---Toshiba-V35-Series-LED-FHD-HD---Fire-TV-(2021)) <br> [fire_tv_4_series](https://github.com/PRProd/HA-Firemote/wiki/Smart-TV---Fire-TV-4-Series-(2021)) <br> [fire_tv_cube_third_gen](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Cube---3rd-Gen-(2022)) <br> [fire_tv_cube_second_gen](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Cube---2nd-Gen-(2019)) <br> [fire_tv_cube_first_gen](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Cube---1st-Gen-(2018)) <br> [fire_tv_stick_4k_max](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Stick-4K-Max---1st-Gen-(2021)) <br> [fire_tv_3rd_gen](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Stick---3rd-Gen-(2020)) <br> [fire_tv_stick_lite](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Stick-Lite---1st-Gen-(2020)) <br> [fire_stick_4k](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Stick-4K---1st-Gen-(2018)) <br> [fire_stick_second_gen](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Stick---2nd-Gen-(2016---2019)) <br> [fire_stick_first_gen](https://github.com/PRProd/HA-Firemote/wiki/Fire-TV-Stick-1st-Gen-(2014)) <br> shield-tv-2017 <br> shield-tv-pro-2017 <br> shield-tv-2019 <br> shield-tv-pro-2019 <br> mi-box-s | The type of device you are controlling<br>[Which devices are supported?](https://github.com/PRProd/HA-Firemote/wiki/Existing-Amazon-Devices---Support-Chart)<br>[Which device do I own?](https://developer.amazon.com/docs/fire-tv/device-specifications.html) |
| compatibility_mode | string | no | default <br> strong <br> event0 <br> event1 <br> event2 <br> event3 <br> event4 <br> event5 <br> event6 <br> event7 <br> event8 <br> event9 <br> event10 <br> event11 <br> event12 <br> event13 | Adjust this value only if your buttons are completely unresponsive<br>[FAQ Available for additional help](https://github.com/PRProd/HA-Firemote#faq) |
|defaultRemoteStyle_override | string | no | AF1 <br> AF2 <br> AF3 <br> AF4 <br> AF5 <br> AF6 <br> CC1 <br> NS1 <br> NS2 <br> XM2 <br> AL1 <br> AL2 | Optionally select a style of remote different from the one that shipped with your device |
| app_launch_1<br>app_launch_2<br>app_launch_3<br>app_launch_4<br>app_launch_5<br>etc... | string | no | [ See App Launch Button Customization section for options](#app-launch-button-customization) | Quick launch apps customization |
|hdmi_1<br>hdmi_2<br>hdmi_3</br>hdmi_4| string | no | Personalized name for this HDMI input | The name entered here will appear on the button (truncated to 8 characters to fit)|
| scale       | integer| no       | Any positive number                                           | Change the size of this card by percentage. The default size is 100 |
| button_overrides | object | no | Button name and HA script name are required.| Details are in the Button Overrides section of the [README.md](https://github.com/PRProd/HA-Firemote/edit/main/README.md#button-overrides) file |
| visible_name_text       | string | no      | Any text                                                         | Optional device label for your firemote|
| name_position           | string | no      | hidden<br>bottom<br>top<br>                                      | Position for your optional device label|
| visible_name_text_color | hex color value | no | Any hex color value e.g.: #ffffff                            | Optional text color for the device name label |
| show_version_number     | bool   | no      | true<br>false                                                    | Optionally display the Firemote Version number on the card|
| hide_button_highlights  | bool   | no      | true<br>false                                                    | Optionally hide the status higlighting decorations for the power, home, and play/pause buttons |

<br>
<br>
<br>

## App Launch Button Customization
Custom app launch buttons are not limited to the few that came printed on your remote control.  In fact, the possibilities are endless!  If you don't see your favorite app on this list, you can click on the [Issues](https://github.com/PRProd/HA-Firemote/issues) button on the top of this page, click 'New Issue' and then click the "Get Started" button next to the "App Shortcut Request" option.  Your request is important to you and likely important to others as well!  As long as the app is easily downloaded through your device's app store (not sideloaded), your request will be granted ASAP.

Options:
| Value for YAML File     | App / Physical Input    | Fire Support | Chromecast Support | Shield Support | Xiaomi Support |
| ----------------------- | ----------------------- | :----------: | :----------------: | :------------: | :------------: |
| abc-iview               | ABC iview (AU)          | ✓            | ✓                  | ✓              | ✓              |
| ace-stream-media        | Ace Stream Media        | ✓            | ✓                  | ✓              | ✓              |
| all-4                   | ALL4                    | ✓            | ✓                  | ✓              | ✓              |
| amc-plus                | AMC+                    | ✓            | ✓                  | ✓              | ✓              |
| app-opener              | App Opener              | ✓            |                    |                |                |
| apple-tv                | Apple TV                | ✓            | ✓                  | ✓              | ✓              |
| bbc-iplayer             | BBC iPlayer (UK)        | ✓            | ✓                  |                |                |
| bell-fibe-tv            | Bell Fibe TV (CA)       | ✓            |                    |                |                |
| cnn                     | CNN                     | ✓            | ✓                  | ✓              | ✓              |
| cosmote-tv              | COSMOTE TV              |              | ✓                  | ✓              | ✓              |
| crave-tv                | Crave TV (CA)           | ✓            |                    |                |                |
| crunchyroll             | Crunchyroll             | ✓            | ✓                  | ✓              | ✓              |
| curiosity-stream        | Curiosity Stream        | ✓            | ✓                  | ✓              | ✓              |
| cyberghost              | CyberGhost VPN          | ✓            | ✓                  | ✓              | ✓              |
| dazn                    | DAZN                    | ✓            | ✓                  | ✓              | ✓              |
| directv-stream          | DIRECTV stream          | ✓            | ✓                  | ✓              | ✓              |
| discovery-plus          | Discovery +             | ✓            | ✓                  | ✓              | ✓              |
| disney-plus             | Disney +                | ✓            | ✓                  | ✓              | ✓              |
| ds-video                | DS Video                | ✓            | ✓                  | ✓              | ✓              |
| emby                    | Emby                    | ✓            | ✓                  | ✓              | ✓              |
| eon-tv                  | EON TV                  |              | ✓                  | ✓              | ✓              |
| ertflix                 | ERT FLIX                |              | ✓                  | ✓              | ✓              |
| espn                    | ESPN                    | ✓            | ✓                  | ✓              | ✓              |
| f-droid                 | F-Droid                 | ✓            | ✓                  | ✓              | ✓              |
| f1-tv                   | F1 TV                   | ✓            | ✓                  | ✓              | ✓              |
| firetv-store            | FireTV Store            | ✓            |                    |                |                |
| freevee                 | freevee                 | ✓            | ✓                  | ✓              | ✓              |
| gcn-plus                | GCN+                    | ✓            | ✓                  | ✓              | ✓              |
| go-play                 | GOPLAY                  | ✓            | ✓                  | ✓              | ✓              |
| go-tv                   | GO TV                   | ✓            | ✓                  | ✓              | ✓              |
| google-play-store       | Google Play Store       |              | ✓                  | ✓              | ✓              |
| hbo-max                 | Max                     | ✓            | ✓                  | ✓              | ✓              |
| home-assistant          | Home Assistant          | ✓            |                    |                |                |
| hulu                    | Hulu                    | ✓            | ✓                  | ✓              |                |
| ipvanish                | IPVanish VPN            | ✓            | ✓                  | ✓              | ✓              |
| israel-station          | Israel Station          | ✓            | ✓                  | ✓              | ✓              |
| jellyfin                | Jellyfin                | ✓            | ✓                  | ✓              | ✓              |
| kayo                    | Kayo Sports (AU)        | ✓            |                    | ✓              | ✓              |
| kodi                    | Kodi                    | ✓            | ✓                  | ✓              | ✓              |
| live-channels           | Live Channels           |              | ✓                  | ✓              | ✓              |
| magenta-tv              | Magenta TV              | ✓            |                    | ✓              | ✓              |
| max-player              | MaxPlayer               | ✓            | ✓                  | ✓              | ✓              |
| mediaset-infinity       | Mediaset Infinity       | ✓            | ✓                  | ✓              | ✓              |
| mediaset-infinity-alt   | Mediaset Infinity (alt) | ✓            | ✓                  | ✓              | ✓              |
| mlb                     | MLB                     | ✓            | ✓                  | ✓              | ✓              |
| movistar-plus           | Movistar Plus+          | ✓            | ✓                  | ✓              | ✓              |
| myCanal                 | my CANAL                | ✓            | ✓                  | ✓              | ✓              |
| my-family-cinema        | My Family Cinema        | ✓            | ✓                  | ✓              | ✓              |
| netflix                 | Netflix                 | ✓            | ✓                  | ✓              | ✓              |
| nebula                  | Nebula                  | ✓            | ✓                  | ✓              | ✓              |
| news                    | News by Fire TV         | ✓            |                    |                |                |
| nine-now                | 9now                    | ✓            | ✓                  | ✓              | ✓              |
| nlziet                  | NLZIET                  | ✓            | ✓                  | ✓              | ✓              |
| nordvpn                 | Nord VPN                | ✓            | ✓                  | ✓              | ✓              |
| now-tv                  | Now TV                  | ✓            |                    |                |                |
| npo                     | NPO (NL)                |              | ✓                  | ✓              | ✓              |
| optus-sport             | Optus Sport (AU)        | ✓            | ✓                  | ✓              | ✓              |
| ott-navigator           | OTT Navigator           | ✓            | ✓                  | ✓              | ✓              |
| oqee-by-free            | OQEE by Free (FR)       | ✓            | ✓                  |                |                |
| pandora                 | Pandora                 | ✓            | ✓                  | ✓              | ✓              |
| paramount-plus          | Paramount+              | ✓            | ✓                  | ✓              | ✓              |
| paramount-plus-de       | Paramount+ (alt)        | ✓            | ✓                  | ✓              | ✓              |
| peacock                 | Peacock                 | ✓            | ✓                  | ✓              | ✓              |
| plex                    | Plex                    | ✓            | ✓                  | ✓              | ✓              |
| prime-video             | Prime Video             | ✓            | ✓                  | ✓              | ✓              |
| private-internet-access | Private Internet Access |              | ✓                  | ✓              | ✓              |
| raiplay                 | RaiPlay (IT)            | ✓            | ✓                  | ✓              | ✓              |
| redplay                 | RedPlay                 | ✓            | ✓                  | ✓              | ✓              |
| sbs-on-demand           | SBS On Demand (AU)      | ✓            | ✓                  | ✓              | ✓              |
| seven-plus              | 7plus (AU)              | ✓            | ✓                  | ✓              | ✓              |
| shaw-bluecurve-tv       | Shaw Bluecurve TV (CA)  | ✓            | ✓                  | ✓              | ✓              |
| shophq                  | ShopHQ                  | ✓            |                    |                |                |
| showtime                | Showtime                | ✓            | ✓                  | ✓              | ✓              |
| sky-news                | Sky News                | ✓            | ✓                  | ✓              | ✓              |
| sky-showtime            | Skyshowtime             | ✓            |                    |                |                |
| sky-sport-now           | Sky Sport Now           | ✓            | ✓                  | ✓              | ✓              |
| smart-tube-next         | Smart Tube Next         | ✓            | ✓                  | ✓              | ✓              |
| smart-tube-next-beta    | Smart Tube Next Beta    | ✓            | ✓                  | ✓              | ✓              |
| spotify                 | Spotify                 | ✓            | ✓                  | ✓              | ✓              |
| stan                    | Stan (AU)               | ✓            | ✓                  | ✓              | ✓              |
| starz                   | Starz                   | ✓            | ✓                  | ✓              | ✓              |
| steam-link              | Steam Link              |              | ✓                  | ✓              | ✓              |
| stream-tv               | StreamTV                | ✓            | ✓                  | ✓              | ✓              |
| streamz                 | streamz (BE)            |              | ✓                  | ✓              | ✓              |
| stremio                 | Stremio                 | ✓            | ✓                  | ✓              | ✓              |
| surfshark-vpn           | Surfshark VPN           | ✓            | ✓                  | ✓              | ✓              |
| svt-play                | SVT Play                |              | ✓                  | ✓              | ✓              |
| t2-tv                   | T-2 TV                  | ✓            | ✓                  | ✓              | ✓              |
| telenet-tv              | Telenet TV (BE)         | ✓            | ✓                  | ✓              | ✓              |
| ten-play                | 10play (AU)             | ✓            | ✓                  | ✓              | ✓              |
| tennis-channel          | Tennis Channel          | ✓            |                    |                |                |
| threenow                | Three Now (NZ)          | ✓            | ✓                  | ✓              | ✓              |
| tidal                   | Tidal                   | ✓            | ✓                  | ✓              | ✓              |
| tivimate                | TiviMate IPTV Player    | ✓            | ✓                  | ✓              | ✓              |
| tubi                    | tubi                    | ✓            | ✓                  | ✓              | ✓              |
| tvexpress-br            | TVExpress (BR)          | ✓            | ✓                  | ✓              | ✓              |
| tvnz-plus               | TVNZ+ (NZ)              | ✓            | ✓                  | ✓              | ✓              |
| twire                   | Twire                   | ✓            | ✓                  | ✓              | ✓              |
| twitch                  | Twitch                  | ✓            | ✓                  | ✓              | ✓              |
| viaplay                 | Viaplay                 | ✓            | ✓                  | ✓              | ✓              |
| videoland               | Videoland (NL)          |              | ✓                  | ✓              | ✓              |
| vlc                     | VLC                     |              | ✓                  | ✓              | ✓              |
| vtm-go                  | VTM GO (BE)             |              | ✓                  | ✓              | ✓              |
| vrt-max                 | VRT MAX (BE)            |              | ✓                  | ✓              | ✓              |
| waipuTV                 | Waipu TV (DE)           | ✓            |                    |                |                |
| xciptv-player           | XCIPTV Player           | ✓            | ✓                  | ✓              | ✓              |
| xfinityStream           | Xfinity Stream          | ✓            |                    | ✓              |                |
| youtube                 | YouTube                 | ✓            | ✓                  | ✓              | ✓              |
| youtubekids             | YouTube Kids            | ✓            | ✓                  | ✓              | ✓              |
| youtubeTV               | YouTube TV              | ✓            | ✓                  | ✓              | ✓              |
| zattoo                  | Zattoo                  | ✓            |                    |                |                |
| ziggo-go                | Ziggo Go                | ✓            | ✓                  | ✓              | ✓              |
| function-app-switch     | Built-in App Switcher   |              | ✓                  | ✓              | ✓              |
| function-find-my-remote | Shield's Remote Locator |              |                    | ✓              |                |
| function-mute           | Mutes your device       | ✓            |                    | ✓              | ✓              |
| function-reboot         | Reboots your device     | ✓            | ✓                  | ✓              | ✓              |
| hdmi_1                  | HDMI Input 1            | ✓ (device specific) |             |                |                |
| hdmi_2                  | HDMI Input 2            | ✓ (device specific) |             |                |                |
| hdmi_3                  | HDMI Input 3            | ✓ (device specific) |             |                |                |
| hdmi_4                  | HDMI Input 4            | ✓ (device specific) |             |                |                |

<br>
<br>
<br>

## Button Overrides
Button Overrides can be very useful for customization.  These overrides can be used to call a Home Assistant service directly, run a script, or hide a button on your remote.  These options are accomplished through your Firemote's YAML configuration.

Consider this example:
```yaml
button_overrides:
  mute-button:
    script: receiver_mute_script
  volume-down-button:
    script: receiver_volume_down_script
  volume-up-button:
    service: light.toggle
    target:
      entity_id: light.bedroom_lamp
    data:
      color_name: red
      transition: 2
      brightness_pct: 100
  power-button:
    hidden: true
```

Valid button names are as follows:
 - power-button
 - headset-button
 - keyboard-button
 - up-button
 - left-button
 - center-button
 - right-button
 - down-button
 - apps-button
 - back-button
 - home-button
 - hamburger-button
 - rewind-button
 - playpause-button
 - fastforward-button
 - volume-up-button
 - channel-up-button
 - volume-down-button
 - tv-button
 - channel-down-button
 - mute-button
 - settings-button
 - app-switch-button
 - input-button
 - programmable-one-button
 - programmable-two-button
 - restart-button
 
<br>
<br>
<br>

## FAQ
###  Why won't the volume, mute, and/or power buttons work from my Firemote card?
In many cases, your remote control sends commands for volume, mute, and power to your TV or receiver using the IR emitter on the front of the physical remote control.  Since this is the case, these IR commands cannot be emulated through the same means that Firemote sends other commands.
<br>

In these cases, you might still have options.  If your Amazon Fire or Android TV media device AND the device they are connected to both offer CEC options, then activating them will allow the Firemote controls to work as expected.  [Click here](https://github.com/PRProd/HA-Firemote/wiki/Using-CEC-Controls) to learn more about how to [configure CEC to work with your Firemote](https://github.com/PRProd/HA-Firemote/wiki/Using-CEC-Controls).  Another option might be to control your devices (TVs, Receivers, etc.) using [Button Overrides](https://github.com/PRProd/HA-Firemote#button-overrides).  If you can control those kinds of devices through Home Assistant, you can write a HA script and attach that script to a button on your Firemote.
<br>
<br>

### Why don't any of the buttons on the Firemote work at all? ###
 * If your Firemote used to work perfectly, and some or all of the buttons suddenly stopped working, it could be that all you need to do is press one button (any button) on your Fire TV device's physical remote control.  After doing that step, try your Firemote again.  This step most commonly fixes the issue in Amazon Fire devices after they are powered on, restarted, or updated.
 * Check your card configuration:
   * Is the correct Android device selected?
   * Is the correct Device Family selected?
   * Is the correct Device type selected?
   * If you are using it, is the correct matching Android TV Remote Entity selected?
   * Is Compatibility Mode set to Default?
 * If the Default Compatibility Mode is not working on your device, and you've checked every other step, slowly choose "event0", "event1", etc. and test your remote buttons under each mode.  One of these will work.
<br>

### Why isn't my Amazon Fire Device supported?
There are over 40 kinds of Amazon Fire devices, so it will take a while to gain properly tested support for all of them.  If Firemote doesn't support your Amazon Fire device yet, you can still use Firemote!  Simply choose a supported device that is similar to the one that you have (preferably a remote that looks the same as your physical remote), then you can test different compatibility modes to find out which one works the best.<br>

For extra credit, you could submit a request to have your device added!  It's simple!  Click on the [Issues](https://github.com/PRProd/HA-Firemote/issues) button on the top of this page, click 'New Issue' and then click the "Get Started" button next to the "Device Support Request" option.  Your help is VERY appreciated!
<br>
<br>

### I want a shortcut button for an app I use frequently, but it's not on the list.  Can it be added?
Absolutely!  Simply ask!  Here's how: Click the [Issues](https://github.com/PRProd/HA-Firemote/issues) button at the top of this page, click 'New Issue' and then click the "Get Started" button next to the "App Shortcut Request" option.  Your request is important to you and likely important to others as well!  If the app is easily downloaded through your device's official store (not sideloaded), your request will be granted ASAP.
<br>
<br>

### How do I report a problem, make a request, or talk about stuff?
Click on the [Issues](https://github.com/PRProd/HA-Firemote/issues) button at the top of this page, click 'New Issue', and select the appropriate category for your needs.  You're also welcome to join or begin a new [discussion](https://github.com/PRProd/HA-Firemote/discussions) if that suits your needs.
<br>
<br>

### How can I contribute?
Take a look at the current [discussions board](https://github.com/PRProd/HA-Firemote/discussions) to see if anything is tagged with "Help Wanted".
