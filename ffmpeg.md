# ffmpeg
ffmpeg 是处理音频文件的工具。
https://ffmpeg.org/
## 安装
```sh
# windows
winget install --source winget -i --id Gyan.FFmpeg # ffmpeg-full
```
---
# 常用参数
```sh
-i # 设定输入流 
-f # 设定输出格式
-ss #开始时间

# 视频参数
-aspect # 设定画面的比例
-r # 设定帧速率，默认为25
-s # 设定画面的宽与高
-vcodec/-c:v # 设定视频编解码器，未设定时则使用与输入流相同的编解码器
-vn # 无视频

# 音频参数
-ar # 音频采样率
-ac # 设定声音的Channel数
-acodec/-c:a # 设定声音编解码器，未设定时则使用与输入流相同的编解码器
-an # 无音频
```

# 提取
```sh
# 提取音频
ffmpeg -i input.mp4 -vn -c:a copy output.aac
ffmpeg -i input.mp4 -vn -b:a 128k -ar 44k -c:a mp3 output.mp3

# 提取视频
ffmpeg -i input.mp4 -an -c:v copy output.mp4

```

# 序列
```sh
# 序列转视频
# 视频转序列
```

# 转换/压缩
```sh

```