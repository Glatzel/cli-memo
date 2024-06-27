# qpdf
qpdf 可以完成对pdf的常用操作，如：合并，拆分，加密等.
## 添加到powshell
将以下内容写入我的文档`C:$env:HOMEPATH/Documents/PowerShell/profile.ps1`
```sh
function qpdf {
    try {& "$env:ProgramFiles/qpdf/bin/qpdf.exe" $args}
    catch {Write-Error "Peazip is not installed."}
}
```
---
# 合并
```sh
qpdf --pages *.pdf -- out.pdf
```

# 拆分
```sh
qpdf --split-pages=n 001.pdf -- 001.pdf # n页为一个pdf，通常为1
qpdf infile.pdf --pages . m-n -- outfile.pdf #提取m-n页，保留原文件的目录格式
qpdf --empty --pages infile.pdf m-n -- outfile.pdf #提取m-n页，不保留原文件的目录格式
```

# 加密解密
```sh
qpdf --password='123456' --decrypt infile.pdf outfile.pdf
```