# 激活windows
管理员
```pwsh
slmgr /skms $server_url #设置kms服务器地址
slmgr /ato # 激活
slmgr /dlv # 查看状态
```

# 开启异类线程调度策略
管理员
```pwsh
# 针对全大核处理器
# 选择电源计划，高性能或者卓越性能都可以
# 更改计划设置—更改高级电源设置—处理器电源管理
# 异类线程调度策略 和 异类短运行线程调度策略
# 这两个都改成所有处理器，再应用确定就可以了
powercfg -attributes SUB_PROCESSOR 93b8b6dc-0698-4d1c-9ee4-0644e900c85d -ATTRIB_HIDE
powercfg -attributes SUB_PROCESSOR bae08b81-2d5e-4688-ad6a-13243356654b -ATTRIB_HIDE
```

# 默认ps1脚本运行方式
cmd 管理员
```cmd
ftype Microsoft.PowerShellScript.1="pwsh" "%1"
```

# ps1脚本运行权限
管理员
```
set-executionpolicy -executionpolicy RemoteSigned
```