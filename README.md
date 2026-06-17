<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff0080,25:ff4400,50:ff0000,75:cc0000,100:8800ff&height=220&section=header&text=YouModExtra&fontSize=78&fontColor=ffffff&fontAlignY=38&desc=✦%20The%20Ultimate%20YouTube%20IPA%20Builder%20✦&descAlignY=60&descSize=22&animation=fadeIn" width="100%"/>

🦖 A powerful GitHub Actions workflow that builds a fully-tweaked YouTube IPA — powered by YouMod and a suite of the best community tweaks, all in one click 🦕

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:8800ff,50:4400ff,100:0044ff&height=80&section=header&reversal=true" width="100%"/>

## 💫🛸 What Is YouModExtra?

**YouModExtra** is a GitHub Actions–powered build system that automatically clones, compiles, and injects a curated set of iOS YouTube tweaks into a decrypted YouTube IPA — producing a sideloadable, feature-packed YouTube experience without a jailbreak.

The centerpiece is **YouMod**, a custom tweak built and maintained right here. Around it, a handpicked collection of the best community-built tweaks are bundled together to create the ultimate YouTube client.
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00ccff,50:00ffaa,100:00ff44&height=80&section=header&reversal=true" width="100%"/>

## ✨ Included Tweaks

| Tweak | Description | Default |
|---|---|---|
| 🔴 **YouMod** | Core tweak — custom settings & enhancements | ✅ On |
| 📺 **YouPiP** | Picture-in-Picture support | ✅ On |
| 🎬 **YTUHD** | Unlock 4K / 8K stream quality | ✅ On |
| 👎 **Return YouTube Dislikes** | Restore dislike counts | ✅ On |
| ⚙️ **YTABConfig** | Unlock hidden A/B config flags | ✅ On |
| 🎯 **YouQuality** | Auto-select preferred video quality | ✅ On |
| 🎚️ **YouSlider** | Color-customizable progress bar | ✅ On |
| 🔇 **YouMute** | Quick mute/unmute toggle | ✅ On |
| 🔁 **YouLoop** | One-tap video looping | ✅ On |
| ⚡ **YouSpeed** | Quick playback speed controls | ✅ On |
| 🗳️ **YTSilentVote** | Vote without visual feedback | ✅ On |
| 🛠️ **YTweaks** | General YouTube refinements | ✅ On |
| 🚫 **iSponsorBlock** | Skip sponsors automatically | ✅ On |
| 📐 **DontEatMyContent** | Fix notch/Dynamic Island layout | ✅ On |
| 🌐 **Open in YouTube** | Safari extension integration | ✅ On |
| 🎨 **Gonerino** | Remove unwanted UI elements | ✅ On |
| 💬 **YouGetCaption** | Enhanced caption controls | ✅ On |
| 🎵 **YouChooseQuality** | Per-video quality selector | ✅ On |
| 👑 **YouPro** | Optional premium UI layer | ❌ Off |

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00ff44,50:aaff00,100:ffcc00&height=80&section=footer" width="100%"/>

## 🏗️ How It Works

```
┌─────────────────────────────────────────────────────┐
│              GitHub Actions Workflow                │
│                                                     │
│  1. You provide a decrypted YouTube .ipa URL        │
│  2. All tweaks are cloned & compiled with Theos     │
│  3. YouMod is built from source (this repo)         │
│  4. cyan injects all .deb files into the IPA        │
│  5. A draft release is created with the final IPA   │
└─────────────────────────────────────────────────────┘
```

The entire pipeline runs on **macOS** runners, uses **Theos** for tweak compilation, and **cyan (pyzule-rw)** for IPA injection. Smart caching ensures previously-built tweaks are reused, keeping build times fast.

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff4400,50:ff0080,100:cc00ff&height=80&section=footer" width="100%"/>

## ▶️ Usage

### Prerequisites

- A **decrypted YouTube IPA** (from a decryption service or your own device)
- A fork of this repository

### Steps

1. **Fork** this repository
2. Go to **Actions → Build YouMod IPA**
3. Click **Run workflow**
4. Fill in the fields:

| Field | Description | Example |
|---|---|---|
| `ipa_url` | Direct URL to your decrypted IPA | `https://example.com/youtube.ipa` |
| `display_name` | App name shown on your device | `YouTube` |
| `bundle_id` | Bundle identifier | `com.google.ios.youtube` |
| Tweak toggles | Enable/disable each tweak | (see defaults above) |

5. Wait for the build to complete (~5–10 min)
6. Find your IPA in **Releases** as a **Draft Release**
7. Download and sideload with [Sideloadly](https://sideloadly.io), [AltStore](https://altstore.io), or your preferred tool
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0099ff,50:00ddcc,100:00ff88&height=80&section=header&reversal=true" width="100%"/>

## 🔧 Workflow Files

```
.github/
└── workflows/
    ├── buildyoumod.yml          ← Main entry point (trigger this)
    └── _build_tweaks.yml        ← Reusable tweak compilation workflow
```

**`buildyoumod.yml`** — The workflow you trigger manually. Accepts all user inputs and passes them to the build pipeline.

**`_build_tweaks.yml`** — The heavy lifter. Installs Theos, clones and compiles every tweak from source, then uploads the built `.deb` files as artifacts.
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ffee00,50:ff9900,100:ff3300&height=80&section=header&reversal=true" width="100%"/>

## 🛠️ Building YouMod Locally

YouMod is built with [Theos](https://theos.dev). To build locally:

```bash
# Install Theos (macOS)
bash -c "$(curl -fsSL https://raw.githubusercontent.com/theos/theos/master/bin/install-theos)"

# Clone and build
git clone https://github.com/PDFMerger2025/YouMod.git
cd YouMod
make clean package DEBUG=0 FINALPACKAGE=1 THEOS_PACKAGE_SCHEME=rootless
```

The compiled `.deb` will be in `packages/`.
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:8800ff,25:ff00cc,50:ff0055,75:ff6600,100:ffcc00&height=80&section=header&reversal=true" width="100%"/>

## 💎 Credits & Acknowledgements

<div align="center">

### 🏆 Built on the shoulders of giants

</div>

A massive, heartfelt shoutout to **[@mrdrvt99](https://github.com/mrdrvt99)** — the original architect behind this entire build system. The GitHub Actions pipeline, the tweak injection workflow, the caching strategy, the Theos integration — **all of it was designed and built by mrdrvt99**. This project simply extends that incredible foundation by integrating YouMod as the centerpiece tweak. Without their work, none of this would exist. Go give them a ⭐ star right now.

<div align="center">
</div>

<br/>

| Tweak | Author | Repo |
|---|---|---|
| YouMod | [@Tonwalter888](https://github.com/Tonwalter888/) | [YouMod](https://github.com/Tonwalter888/YouMod) |
| YouPiP | [@PoomSmart](https://github.com/PoomSmart) | [YouPiP](https://github.com/PoomSmart/YouPiP) |
| YTUHD | [@Tonwalter888](https://github.com/Tonwalter888) | [YTUHD](https://github.com/Tonwalter888/YTUHD) |
| Return YouTube Dislikes | [@PoomSmart](https://github.com/PoomSmart) | [Return-YouTube-Dislikes](https://github.com/PoomSmart/Return-YouTube-Dislikes) |
| YTABConfig | [@PoomSmart](https://github.com/PoomSmart) | [YTABConfig](https://github.com/PoomSmart/YTABConfig) |
| YouQuality | [@PoomSmart](https://github.com/PoomSmart) | [YouQuality](https://github.com/PoomSmart/YouQuality) |
| YouSlider | [@PoomSmart](https://github.com/PoomSmart) | [YouSlider](https://github.com/PoomSmart/YouSlider) |
| YouMute | [@PoomSmart](https://github.com/PoomSmart) | [YouMute](https://github.com/PoomSmart/YouMute) |
| YouLoop | [@bhackel](https://github.com/bhackel) | [YouLoop](https://github.com/bhackel/YouLoop) |
| YouSpeed | [@PoomSmart](https://github.com/PoomSmart) | [YouSpeed](https://github.com/PoomSmart/YouSpeed) |
| YTSilentVote | [@PoomSmart](https://github.com/PoomSmart) | [YTSilentVote](https://github.com/PoomSmart/YTSilentVote) |
| YTweaks | [@fosterbarnes](https://github.com/fosterbarnes) | [YTweaks](https://github.com/fosterbarnes/YTweaks) |
| iSponsorBlock | [@Galactic-Dev](https://github.com/Galactic-Dev) | [iSponsorBlock](https://github.com/Galactic-Dev/iSponsorBlock) |
| DontEatMyContent | [@therealFoxster](https://github.com/therealFoxster) | [DontEatMyContent](https://github.com/therealFoxster/DontEatMyContent) |
| Gonerino | [@castdrian](https://github.com/castdrian) | [Gonerino](https://github.com/castdrian/Gonerino) |
| YouGetCaption | [@PoomSmart](https://github.com/PoomSmart) | [YouGetCaption](https://github.com/PoomSmart/YouGetCaption) |
| YouChooseQuality | [@Tonwalter888](https://github.com/Tonwalter888) | [YouChooseQuality](https://github.com/Tonwalter888/YouChooseQuality) |
| Alderis | [@hbang](https://github.com/hbang) | [Alderis](https://github.com/hbang/Alderis) |
| IAmYouTube | [@PoomSmart](https://github.com/PoomSmart) | [IAmYouTube](https://github.com/PoomSmart/IAmYouTube) |
| YouGroupSettings | [@PoomSmart](https://github.com/PoomSmart) | [YouGroupSettings](https://github.com/PoomSmart/YouGroupSettings) |
| YouPro | [@mrdrvt99](https://github.com/mrdrvt99) | [YouPro](https://github.com/mrdrvt99/YouPro) |
| Open in YouTube | [@BillyCurtis](https://github.com/BillyCurtis) | [OpenYouTubeSafariExtension](https://github.com/BillyCurtis/OpenYouTubeSafariExtension) |
| YouTubeHeader | [@PoomSmart](https://github.com/PoomSmart) | [YouTubeHeader](https://github.com/PoomSmart/YouTubeHeader) |
| YTVideoOverlay | [@PoomSmart](https://github.com/PoomSmart) | [YTVideoOverlay](https://github.com/PoomSmart/YTVideoOverlay) |
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff0055,50:aa0088,100:550099&height=80&section=header&reversal=true" width="100%"/>

## ⚠️ Disclaimer

This project is intended for **personal use only**. Sideloading modified apps may violate Apple's Terms of Service and YouTube's Terms of Service. Use at your own risk. No warranty is provided. This project is not affiliated with, endorsed by, or connected to Apple Inc. or Google LLC in any way.

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:550099,25:8800cc,50:cc0099,75:ff0055,100:ff4400&height=130&section=footer&animation=fadeIn" width="100%"/>

<div align="center">

*Built with ❤️ on top of the incredible work by [@mrdrvt99](https://github.com/mrdrvt99)*

</div>
