# Nftables 批量转发
## 一、快速安装
```bash
curl -fsSL https://raw.githubusercontent.com/outmcn/Nftables/main/nfter.sh | sudo bash
```
## 二、启动工具
```bash
sudo nfter
```
## 三、卸载程序

```bash
# 1. 停止并禁用开机自启服务
sudo systemctl stop nfter
sudo systemctl disable nfter

# 2. 删除主程序文件
sudo rm -f /usr/local/bin/nfter
sudo rm -f /etc/systemd/system/nfter.service

# 3. 删除配置文件+日志（可选，建议执行）
sudo rm -rf /etc/nfter
sudo rm -f /var/log/nfter.log
sudo rm -f /var/run/nfter-daemon.pid

# 4. 刷新 systemd 配置
sudo systemctl daemon-reload

# 5. 清空所有 nftables 转发规则（谨慎！会清空全部端口转发）
sudo nft flush table ip nat
sudo nft flush table ip6 nat
```
