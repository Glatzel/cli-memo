# 压缩图片
```sh
magick input.png -resize 800x600 -quality 92 output.jpg
```
---
# 堆栈
```sh
# 查看堆栈方法
magick -list evaluate
# 平均值堆栈
magick input-*.png -evaluate-sequence mean -depth 16 out.tiff 
```