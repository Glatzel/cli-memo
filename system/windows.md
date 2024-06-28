

---
---

# 激活windows
```pwsh
slmgr /skms $server_url #设置kms服务器地址
slmgr /ato # 激活
slmgr /dlv # 查看状态
```