## Pipe to Clipboard on Fedora (GNOME)

### For [[Wayland]] (default GNOME session):

```bash
some_command | wl-copy
```

### Core YouTube CLI commands

**Play a video**

```bash
mpv https://www.youtube.com/watch?v=VIDEO_ID
```

**Play audio only**

```bash
mpv --no-video https://www.youtube.com/watch?v=VIDEO_ID
```

**Search and play first result**

```bash
mpv "ytsearch1:search terms"
```

**Download a video**

```bash
yt-dlp https://www.youtube.com/watch?v=VIDEO_ID
```

**Download best video and audio**

```bash
yt-dlp -f bestvideo+bestaudio https://www.youtube.com/watch?v=VIDEO_ID
```

**Download audio as MP3**

```bash
yt-dlp -x --audio-format mp3 https://www.youtube.com/watch?v=VIDEO_ID
```

**Search without playing**

```bash
yt-dlp "ytsearch5:search terms"
```

**Download all videos from a channel**

```bash
yt-dlp https://www.youtube.com/@channelname/videos
```

**Avoid re-downloading**

```bash
yt-dlp --download-archive archive.txt CHANNEL_URL
```

**Terminal UI search and play**

```bash
ytfzf
```

