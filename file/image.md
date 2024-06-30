# 缩放/转换
```sh
# 单张图片
magick input.png -resize 800x600 -quality 92 output.jpg
# 多张jpg转png到./new_folder
magick mogrify -format png -path ./new_folder *.jpg 
# 多张jpg缩放50%
magick mogrify -format jpg -resize 50% *.jpg
# svg 转png
magick -background none -size 1000x1000 in.svg out.png
```

---
# 堆栈
## imagemagick
> [!WARNING]  
> 截至2024-06-30，imagemagick仅支持16bit图像，即使编译使用Q32-HDR选项。
```sh
# 查看堆栈方法
magick -list evaluate
# 平均值堆栈
magick input-*.png -evaluate-sequence mean -depth 16 out.tiff 
```
## oiiotool
```sh
$imgs=Get-ChildItem *.exr
$count=@($imgs).Count
hoiiotool ($imgs).fullname --add --divc "$count.0" -o out.exr
```