# 提取
```sh
# 提取音频
ffmpeg -i input.mp4 -vn -c:a copy output.aac
ffmpeg -i input.mp4 -vn -b:a 128k -ar 44k -c:a mp3 output.mp3

# 提取视频
ffmpeg -i input.mp4 -an -c:v copy output.mp4
```
---
# 视频和图片序列
```sh
# 图片序列转视频
ffmpeg -r 60 -s 1920x1080 -i pic%04d.png -vcodec libx264 -crf 25  -pix_fmt yuv420p test.mp4
# 视频转图片序列
ffmpeg -i a.mp4 -vf fps=$nimages/$perseconds frames/out-%03d.png
```
---
# 转换/压缩
```sh
# 直接转换格式，不做任何修改
ffmpeg -i input.mkv output.mp4
```