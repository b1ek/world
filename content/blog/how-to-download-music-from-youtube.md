+++
template = 'custom/blog-post.html'

title = 'how to download music from youtube + thumbnail'
description = 'a short small guide on how to download music from youtube, preserving thumbnail'
date = '2024-08-22'
slug = 'download-music-from-yt'
year = 2024
month = 8
day = 22
lang = 'en'

[extra]
author = 'b1ek <me@blek.codes>'

+++

# let's get to the point.
you need to have `yt-dlp` and `ffmpeg` installed, `magick` and `lame` for setting the mp3 cover.

`yt-dlp` has the `-x` option, which automatically extracts the audio with ffmpeg. to specify the file format, use `--audio-format` (mp3, aac, etc):

```
yt-dlp https://youtu.be/oLnq2SdZvQs -x --audio-format mp3 -o flying_north.mp3
```

as you can see, the thumbnail is not preserved by `yt-dlp`:

<img src='/blog-image/yt-music-no-thumb.png' />

to get the thumbnail, do:

```
curl https://i.ytimg.com/vi_webp/$VIDEO_ID/maxresdefault.webp -o file.webp
```

to convert it to JPEG + crop it to 1:1 aspect ratio:

```
magick convert -crop 1:1 -gravity center file.{webp,jpeg}
```

and the last thing, to embed it inside the `.mp3`:

```
lame --ti file.jpeg flying_north.mp3
mv flying_north.mp3.mp3 flying_north.mp3 # there's a good chance `lame` will export the file to `FILENAME.mp3.mp3`
```

so, basically it could be collapsed down to a bash script:

```bash
#!/usr/bin/env bash

VIDEO_ID=oLnq2SdZvQs
filename=file.mp3
cover=$(mktemp)

yt-dlp https://youtu.be/$VIDEO_ID -x --audio-format mp3 -o $filename
curl https://i.ytimg.com/vi_webp/$VIDEO_ID/maxresdefault.webp -o $cover
lame --ti $cover $filename
```

and, yay! it works

<img src='/blog-image/yt-music-works-in-amberol.png' />

