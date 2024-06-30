# README模板
````md
# [命令行工具名称](官网链接) [命令名称]
简要描述，体现可以实现的功能，如可以操作pdf文件.

## 安装
### windows
```pwsh

```
### linux
```sh

```
## 主要参数
```sh
-a # 描述
-b # 描述
```
````
---
---
# [aria2](https://aria2.github.io/) [aria2c]
aria2 是一个用于下载文件的工具。

## 安装
### windows
```pwsh
winget install --source winget -i --id aria2.aria2
```
## 主要参数
```sh
-c --continue # 开启断点续传
-d # 下载目录
-i # 从文件读取url
-j --max-concurrent-downloads # 最大同时下载任务数，默认5
-s --split # 最大总连接数量，默认5
-x --max-connection-per-server # 每个服务器最大连接数量，默认1
```
---

# [ffmpeg](https://ffmpeg.org/) [ffmpeg, ffplay, ffprobe]
ffmpeg 是处理音频文件的工具。

## 安装
### windows
```pwsh
winget install --source winget -i --id Gyan.FFmpeg # ffmpeg-full
```
## 主要参数
```sh
-i # 设定输入流 
-f # 设定输出格式
-ss #开始时间

# 视频参数
-aspect # 设定画面的比例
-r # 设定帧速率，默认为25
-s # 设定画面的宽与高
-vcodec -c:v # 设定视频编解码器，未设定时则使用与输入流相同的编解码器
-vn # 无视频

# 音频参数
-ar # 音频采样率
-ac # 设定声音的Channel数
-acodec -c:a # 设定声音编解码器，未设定时则使用与输入流相同的编解码器
-an # 无音频
```
---
# [oiiotool](https://openimageio.readthedocs.io/en/latest/oiiotool.html) [hoiiotool]
oiiotool 是可以用于图像批处理的工具,支持32bit，支持oiio。
## 安装
### windows
1. 安装houdini
2. powershell 配置
```pwsh
function hoiiotool { 
$hpath= Get-ChildItem "$env:ProgramFiles/Side Effects Software/Houdini ??.?.???" | Sort-Object -Property Name -Descending | select -first 1 
& "$hpath/bin/hoiiotool.exe" @args
}
```

# [imagemagick](https://imagemagick.org/) [magick]
imagemagick 是可以用于图像批处理的工具。
> [!WARNING]  
> 截至2024-06-30，即使编译使用Q32-HDR选项，imagemagick最高也仅能支持16bit图像。

## 安装
### windows
```pwsh
winget install --source winget -i --id ImageMagick.ImageMagick
```
## 主要参数
```sh
# 图像尺寸
# https://imagemagick.org/script/command-line-processing.php#:~:text=the%20geometry%20argument.-,size,-General%20description%20(actual
"200%" # 放大2倍
"200x50%" # 200px宽，高度缩放为50% 
"200" # 宽度200px，高度按比例缩放
"x200" # 高度200px，宽度按比例缩放
"200x100" # 按比例缩放到目标尺寸200px*100px，取目标尺寸宽高中较大值
"200x100^" # 按比例缩放到目标尺寸200px*100px，取目标尺寸宽高中较小值
"200x100!" # 按缩放到目标尺寸200px*100px，宽高比例可能变化
```
---
# [peazip](http://www.peazip.org/) [7z, pea, zstd]
peazip 是用于创建和解压归档文件的命令行工具，整合了7z，gzip，zstd等工具。

## 安装
### windows
```pwsh
winget install --source winget -i --id Giorgiotani.Peazip
```
powershell 配置
```sh
function 7z { 
    try { & "$env:ProgramFiles/PeaZip/res/bin/7z/7z.exe" @args }
    catch { Write-Error "Peazip is not installed." } 
}
function pea {
    try { & "$env:ProgramFiles/PeaZip/pea.exe" @args }
    catch { Write-Error "Peazip is not installed." } 
}
function zstd {
    try { & "$env:ProgramFiles/PeaZip/res/bin/zstd/zstd.exe" @args }
    catch { Write-Error "Peazip is not installed." } 
}
```
---

# [qpdf](https://github.com/qpdf/qpdf)
qpdf 可以完成对pdf的常用操作，如：合并，拆分，加密等.

## 安装
### windows
```pwsh
winget install --source winget -i --id QPDF.QPDF
```
powershell 配置
```sh
function qpdf{
    try {& "$env:ProgramFiles/qpdf/bin/qpdf.exe" @args}
    catch {Write-Error "Peazip is not installed."}
}
```
## 主要参数
```sh
--pages # https://qpdf.readthedocs.io/en/stable/cli.html#id25
```
---

# tar
tar 是用于创建和解压归档文件的命令行工具。
https://www.gnu.org/software/tar/

---
