# imagemagick
imagemagick 是可以用于图像批处理的工具。
## 安装
```sh
# windows
winget install --source winget -i --id ImageMagick.ImageMagick # Q16-HDR, 仅支持16bit图像
```
---
# 压缩图片
```sh
magick input.png -resize 800x600 -quality 92 output.jpg

# resize 格式
"200%" # 放大2倍
"200x50%" # 200px宽，高度缩放为50% 
"200" # 宽度200px，高度按比例缩放
"x200" # 高度200px，宽度按比例缩放
"200x100" # 按比例缩放到目标尺寸200px*100px，取目标尺寸宽高中较大值
"200x100^" # 按比例缩放到目标尺寸200px*100px，取目标尺寸宽高中较小值
"200x100!" # 按缩放到目标尺寸200px*100px，宽高比例可能变化
# 参考
# https://imagemagick.org/script/command-line-processing.php#:~:text=the%20geometry%20argument.-,size,-General%20description%20(actual
```

# 堆栈
```sh
# 查看堆栈方法
magick -list evaluate
# 发行版只支持16bit
magick input-*.exr -evaluate-sequence mean -depth 16 out.exr 
```