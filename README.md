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
  InnerSpeaker) title="Tame Impala - InnerSpeaker (Live From Wave House)"
       url="https://www.youtube.com/watch?v=d33C8IE7WnQ" ;;  
  *)
    echo "fm.radio: unknown track '${1}'"
    echo ""
    echo "Available tracks:"
    echo "  fm.radio InnerSpeaker  →  Tame Impala - InnerSpeaker (Live From Wave House)"    
    exit 1
    ;;
esac

echo "▶ fm.radio · $title"
mpv --no-video \
    --term-osd-bar \
    --force-media-title="fm.radio · $title" \
    "$url"
```
