## What is streaming and live streaming?
### Streaming
**Streaming** is the method of data transmission used when someone watches video on the Internet. It is a way to deliver a video file a little bit at a time, often from a remote storage location. By transmitting a few seconds of the file at a time over the internet

### Live Streaming
**Live streaming** is when the streamed video is sent over the Internet in real time, without first being recorded and stored.

## How live streaming work
- **Compression:** The data is compressed by removing redundant visual information. 
- **Encoding**: the process of converting data into a new format. Live streaming video data is encoded into digital format that a wide variety of devices recognize.(H.264, H.265, VP9, AV1)
- **Segmentation**: streaming video is divided into smaller segments a few seconds in length.
- **CDN**: A CDN will cache – temporarily save – each segment of the live stream, so most viewers will get the live stream from the CDN cache instead of from the origin server.
- **Decode**: user's device receives, decodes, and decompresses the segmented video data
- **Video playback**: browser – interprets the data as visual information, and the video plays.

## what is the difference between transcode and encode?
- **Transcode**: is the process of creating copies of video files in different sizes.
- **Encode**: refers to either the initial process of compressing RAW video or to the process of re-encoding a video into a different format.
### why transcode?
- Reduce file size
- Reduce buffering for streaming video
- Change video resolution or aspect ratio
- Change audio format or quality
- Convert obsolete files to modern formats
- Meet a certain target bitrate
- Make a video compatible with a certain device (computer, tablet, smartphone, smartTV, legacy devices)
- Make a video compatible with certain streaming software or service
## What is bitrate?
**Video bitrate** is the amount of video data processed and sent in a given amount of time. It is usually measured in bits per second (kbps), representing the amount of data (in bits) that is encoded for each second of video playback.

Two type of video bitrate:
- **Constant Bitrate (CBR)**: 
- **Variable Bitrate or VBR**

## Some other definition
- **Video resolution**: Resolution of video or monitor. For example, a video might have a resolution of 1280 (horizontal pixels) × 720 (vertical pixels). This is usually written as simply 1280×720, or abbreviated to 720p.
- **Frame rate** is the number of frames that display per second in a video **(fps)**. The faster the frames flicker along, the more lifelike and immersive the video becomes. Common frame rates are 24, 25, 30, and 60 fps
- **Video** **aspect ratio** refers to the proportional relationship between the width and height of the video. This is usually expressed in the width to height format. For example, most modern television and computer monitors have an aspect ratio of 16:9
## Recommend bitrate
Video: **Codec**
Codec: **H.264 (AVC)**
Audio Codec: **AAC**
Frame Rate: **24, 30, or 60 fps**

>480p (SD)
>Bitrate: 1,000 - 2,500 kbps
>Audio Bitrate: 128 kbps

>720p (HD)
>Bitrate: 2,500 - 5,000 kbps
>Audio Bitrate: 192 kbps

>1080p (Full HD)
>Bitrate: 5,000 - 10,000 kbps
>Audio Bitrate: 256 kbps


