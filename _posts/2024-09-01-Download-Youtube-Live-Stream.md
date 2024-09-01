---
layout: post
category: tutorial
---

Downloading specific segments from a YouTube live stream, like the last few hours of content, requires a combination of powerful tools such as `yt-dlp`. While `yt-dlp` is highly effective for downloading YouTube videos and live streams, downloading specific segments isn't directly supported.

## Install 

```bash
pip install yt-dlp
```
Or
```bash
sudo wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -O /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/yt-dlp
```

## Usage

For example, if you want to download this [Shinjuku Live](https://www.youtube.com/watch?v=gFRtAAmiFbE)
```bash
yt-dlp -o "[OUTPUT FILENAME]" --live-from-start -f "bestvideo"  "https://www.youtube.com/watch?v=gFRtAAmiFbE"
```

> Unfortunately, we are unable to download live streams within a specific time frame.

But, if you want to record like 6 hours from now, you can add a `timeout` command in front of the command

```bash
timeout 6h yt-dlp -o "[OUTPUT FILENAME]" --live-from-start -f "bestvideo"  "https://www.youtube.com/watch?v=gFRtAAmiFbE"
```

Ensure `bestvideo` is used because it enables us to get the best resolution.

![Example](/assets/images/2024-09-01/example.png)