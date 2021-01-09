+++
title="Basic ffmpeg reference"
author="Nikhil Raghav"
date="2020-09-19"
nomath=true
description="Basic and most used ffmpeg, notes for reference"
showFullcontent=false
tags=["media", "linux", "reference"]
+++

#### 1. Converting to some format
```bash
ffmpeg -i input.mp3 output.m4a
```

#### 2. Merging audio and video
- Can change final container (mkv is most versatile), ffmpeg automatically decides the decoders for the job.
```bash
ffmpeg -i audio.mp3 -i video.mp4 -c copy merged_video.mkv
```
#### 3. Keeping Output quality same as Input quality (-sameq)
```bash
ffmpeg -i input.avi -sameq output.mkv
```
#### 4. Convert only first 30 seconds (-t)
```bash
ffmpeg -i aadat.mp3 -t 30 aadatintro.mp3
```
- `-t` also supports `hh:mm:ss` as time format
- Variation of this can be used to cut a part of the video, `-ss` flag sets the start time. So set the start time with `-ss` and duration with `-t`
```bash
ffmpeg -i aadat.mp3 -ss 1:12 -t 1:00 solo.mp3
```
#### 5. Strip audio or video 
- `-an` removes audio and `-vn` strips video 
```bash
ffmpeg -i video.mp4 -vn audio.mp3
```
#### 6. Bitrate
- `-ab` sets the audio bitrate and `-b` sets the video bitrate explicitly
```bash
ffmpeg -i audio.mp3 -ab 128k audiocompressed.mp3
```

#### Notes
- default bitrate for video is 200kbps and 64 kbps for audio
- ffmpeg options are always applied to next file in argument list, can be input or ouput file.
- RTFM for more
