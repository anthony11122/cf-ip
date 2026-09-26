# Cloudflare CDN 优选 IPv4 节点池 (Asia / 亚洲区域)

[![Auto Update](https://img.shields.io/badge/Auto%20Update-3%20Times%20Daily-brightgreen.svg)]()
[![Region](https://img.shields.io/badge/Region-Asia%20IPv4-blue.svg)]()
[![License](https://img.shields.io/badge/License-MIT-orange.svg)]()

基于 [cfnb](https://github.com/xinyitang3/cfnb) 算法引擎，每天 3 次（北京时间 06:00、14:00、22:00）全自动执行：
- **多源节点聚合**：汇聚全网活跃 Cloudflare IPv4 节点池
- **前置过滤**：严格仅保留亚洲区域（香港 HK、台湾 TW、新加坡 SG、日本 JP、韩国 KR、马来西亚 MY 等）及 TLS 443 端口
- **TCP 并发延迟测试**：快速探测节点往返握手延迟
- **可用性与 HTTP 探测**：剔除非 Cloudflare 响应节点与失效代理
- **真实带宽与抖动压测**：基于实际 curl 下载测速与方差分析，综合加权输出全局最优节点

---

## 🔗 永久固定订阅与获取链接

本仓库为公开（Public）仓库，下列链接永久固定，每次自动化测试完成后自动同步最新优选结果：

### 1. GitHub 官方 Raw 直链（适合境外/带前置代理环境）
```text
https://raw.githubusercontent.com/anthony11122/cf-ip/main/ip.txt
```

### 2. jsDelivr 全球 CDN 加速链接（国内环境直连极速，自动分发）
```text
https://cdn.jsdelivr.net/gh/anthony11122/cf-ip@main/ip.txt
```

### 3. 国内加速镜像（适合无代理环境直接拉取）
```text
https://ghproxy.net/https://raw.githubusercontent.com/anthony11122/cf-ip/main/ip.txt
```

---

## 📋 节点格式说明

输出文件 `ip.txt` 遵循通用标准格式：
```text
IP地址:端口#国家或地区代码
```
例如：
```text
104.16.x.x:443#HK
162.159.x.x:443#SG
104.18.x.x:443#JP
```
可直接粘贴至 EdgeTunnel、V2Ray、Clash、Sing-box、Shadowrocket 等客户端的 CDN 优选 IP / PROXYIP 配置项中使用。

---

## ⏰ 更新频率

- **更新周期**：每日 3 次
- **执行时间**：06:00 / 14:00 / 22:00 (CST)
- **部署环境**：家庭内部局域网专用服务器自动化 Cron 调度
