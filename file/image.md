# 压缩/缩放/转换
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
> Imagemagick使用与最大值最小值堆栈。
> 平均值堆栈推荐使用[oiiotool](#oiiotool)
```sh
# 查看堆栈方法
magick -list evaluate
# 平均值堆栈
magick input-*.png -evaluate-sequence mean -depth 16 out.tiff 
```
## oiiotool
powershell
```pwsh
function stack_mean($ext = "exr", $dir = $pwd, $out_stem = "out") {
    $imgs = Get-ChildItem "$dir/*.$ext"
    $count = @($imgs).Count
    $out_file = "$dir/$out_stem.exr"
    if (“$out_stem.exr" -in $imgs.Name) {
        Write-Error "$out_stem.$ext in input image files."
        return -1
    }
    $option = @("--info", $imgs[0])
    for ($i = 1; $i -lt $count; $i = $i + 1) {
        $option += $imgs[$i], "-add"
    }
    $option += "-divc", "$count.0", "-o", "$out_file"
    hoiiotool  $option
}
stack_mean
```

# 图片信息
```sh
magick identify -verbose a.png
```