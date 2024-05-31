## HLS - HTTP live streaming
HLS used for both on-demand streaming and live streaming. HLS breaks down video files into smaller downloadable HTTP files and delivers them using the HTTP protocol **(TCP)**

**Advantage**:
- All Internet-connected devices support HTTP
- Increase or decrease video quality depending on network conditions without interrupting playback. This feature is known as "adaptive bitrate video delivery" or "adaptive bitrate streaming"

## How HLS work?
**Server**: HLS stream originate where stream media is stored (in on-demand streaming) or created (in live streaming)
Two main process take place on server:
- **Encode**: The video data is reformatted so that any device can recognize and interpret the data. HLS must use [[StreamingEncoding#Video Codec format|H.264]] or [[StreamingEncoding#Video Codec format|H.265]] encoding.
- **Segmenting:** The video is divided up into segments a few seconds in length. The length of the segments can vary, although the default length is 6 seconds (until 2016 it was 10 seconds).
	- In addition to dividing the video into segments, HLS creates an index file of the video segments to record the order they belong in.
	- HLS will also create several duplicate sets of segments at different quality levels: 480p, 720p, 1080p, and so on.
- **Distribution**: Use CDN to distribute to client 
- **Client device**: receives the stream and plays the video. The client device uses the index file as a reference for assembling the video in order, and it switches from higher quality to lower quality picture (and vice versa) as needed.
## HLS file format
HLS itself doesn't technically define a single file format. It uses a combination of formats to deliver streamed content:
- After encoded input video, HTTP streaming server will create **.m3u8 playlist file** (manifest file) that server serves as an index for video chunks
- The video chunks are often delivered in **MPEG-2 Transport Stream (.ts)** format. This format can hold both video and audio data.

## How to calculate .ts file?
```
Kích thước file .ts (MB) ≈ (Bitrate (Mbps) * Thời lượng phân đoạn (giây)) / (8 * 1024)
```

**Ví dụ:**

- Bitrate: 2Mbps
- Thời lượng phân đoạn: 5 giây

`Kích thước file .ts (MB) ≈ (2 * 5) / (8 * 1024) ≈ 0.625 MB`