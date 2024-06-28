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
```sh
# 查看堆栈方法
magick -list evaluate
# 平均值堆栈
magick input-*.png -evaluate-sequence mean -depth 16 out.tiff 
```