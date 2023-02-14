## ffmpeg

#### Merge audio and video

```
ffmpeg -i video.mp4 -i audio.mp3 -c:v copy -map 0:v -map 1:a -y output.mp4 
```
