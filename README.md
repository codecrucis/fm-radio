# Focus Music (FM) Radio

A terminal application to play music while you work, study, focus, etc.

Make heavy use of tools like mpv for the hard stuff. 


## Getting Started

The easiest way to get started is to collect a set of audio that is already hosted somewhere online. This could be .mp3 files in object storage, YouTube videos, etc. 

Create a new file: `~/.local/bin/fm.radio` and paste the following contents to get started.

```
#!/usr/bin/env bash

key="${1#--}"

case "$key" in
  001) title="Mod:0 - Lofi Hip Hop x Synthwave Session: Code, Focus, Build"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/LofiSynthwaveMix_30M_ChillCoding_2024-10-31.mp3" ;;
  002) title="Codewave on Autopilot – Escape to a Coding Paradise"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/vaporwave.mp3" ;;
  003) title="Lofi Lockdown – An Hour of Coding Zen"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/lofi-coding.mp3" ;;
  004) title="Rainy Lofi – Debugging Under the Streetlight"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Rainy_Lofi_Beats.mp3" ;;
  005) title="Pixel Sunset – Floating Through the Dream Grid"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/vaporwave2.mp3" ;;
  006) title="Golden Hour Grooves – Chillhop for Focus & Flow"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/chillhop.mp3" ;;
  007) title="Escape the Machine – Synthwave for Deep Focus & Code Flow"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/codewave.mp3" ;;
  008) title="Lofi Coding Mix That Calms Your Brain – A Ghibli Dream for Developers"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Lofi_Ghibli_Style_Coding.mp3" ;;
  009) title="Mod:1 – Chillwave x Synthwave Coding Mix – Music for Developers"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Chillwave_Coding_Mix.mp3" ;;
  010) title="Lofi Coding Vibes That Actually Keep You in Flow – Chillhop for Deep Dev Work"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Chillhop_for_programmers.mp3" ;;
  011) title="Back to 1984 // Coding Never Looked This Synthy"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Chill_Vaporwave_Coding.mp3" ;;
  012) title="Still Coding Like It's BACK TO 1984 // Vaporwave Vol II"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Vaporwave_volII.mp3" ;;
  013) title="Synthwave Coding Mix – SPRINT MODE // TERMINAL 1987"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/SyntwaveCodingMix_Terminal1987.mp3" ;;
  014) title="Vaporwave Coding Mix Vol. III – Feels Like 1984"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Vaporwave_Coding_mix_VolIII-feels_like_1984.mp3" ;;
  015) title="Synthwave Coding Mix v1.0 – Terminal 1987"
       url="https://devsfm-audio.sfo2.cdn.digitaloceanspaces.com/Feels_like_Terminal1987-v1.0.mp3" ;;
  *)
    echo "devs.fm: unknown track '${1}'"
    echo ""
    echo "Available tracks:"
    echo "  devs.fm 001  →  Mod:0 - Lofi Hip Hop x Synthwave Session"
    echo "  devs.fm 002  →  Codewave on Autopilot"
    echo "  devs.fm 003  →  Lofi Lockdown"
    echo "  devs.fm 004  →  Rainy Lofi"
    echo "  devs.fm 005  →  Pixel Sunset"
    echo "  devs.fm 006  →  Golden Hour Grooves"
    echo "  devs.fm 007  →  Escape the Machine"
    echo "  devs.fm 008  →  Lofi Ghibli Dream"
    echo "  devs.fm 009  →  Mod:1 Chillwave x Synthwave"
    echo "  devs.fm 010  →  Lofi Coding Vibes"
    echo "  devs.fm 011  →  Back to 1984"
    echo "  devs.fm 012  →  Vaporwave Vol II"
    echo "  devs.fm 013  →  Sprint Mode Terminal 1987"
    echo "  devs.fm 014  →  Vaporwave Vol III"
    echo "  devs.fm 015  →  Synthwave v1.0 Terminal 1987"
    exit 1
    ;;
esac

echo "▶ devs.fm · $title"
mpv --no-video \
    --term-osd-bar \
    --force-media-title="devs.fm · $title" \
    "$url"
```
