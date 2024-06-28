# 合并
```sh
qpdf --pages *.pdf -- out.pdf
```
---
# 拆分
```sh
qpdf --split-pages=n 001.pdf -- 001.pdf # n页为一个pdf，通常为1
qpdf infile.pdf --pages . m-n -- outfile.pdf #提取m-n页，保留原文件的目录格式
qpdf --empty --pages infile.pdf m-n -- outfile.pdf #提取m-n页，不保留原文件的目录格式
# --pages 格式参考
# https://qpdf.readthedocs.io/en/stable/cli.html#id25
```
---
# 加密解密
```sh
qpdf --password='123456' --decrypt infile.pdf outfile.pdf
```
---
# pdf转图片
```sh
```