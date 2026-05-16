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

### 1. 停止并禁用服务
```bash
sudo systemctl stop nfter
sudo systemctl disable nfter
```
### 2. 删除程序文件
```bash
sudo rm -f /usr/local/bin/nfter
sudo rm -f /etc/systemd/system/nfter.service
```
### 3. 删除配置和日志（可选）
```bash
sudo rm -rf /etc/nfter
sudo rm -f /var/log/nfter.log
sudo rm -f /var/run/nfter-daemon.pid
```
### 4. 重载 systemd
```bash
sudo systemctl daemon-reload
```
### 5. 清空转发规则（可选，谨慎操作）
```bash
sudo nft flush table ip nat
sudo nft flush table ip6 nat
```
