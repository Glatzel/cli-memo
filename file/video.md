# 提取
```sh
# 提取音频
ffmpeg -i input.mp4 -vn -c:a copy output.aac
ffmpeg -i input.mp4 -vn -b:a 128k -ar 44k -c:a mp3 output.mp3

# 提取视频
ffmpeg -i input.mp4 -an -c:v copy output.mp4
```
---
# 视频转图片序列
```sh
```
---
# 转换/压缩
