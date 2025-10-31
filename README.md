# 🌐 AWS IP Ranges (Amazon Web Services)

This repository provides regularly updated **Amazon Web Services (AWS)** IP ranges, sourced directly from the official endpoint:
🔗 [https://ip-ranges.amazonaws.com/ip-ranges.json](https://ip-ranges.amazonaws.com/ip-ranges.json)

## 📁 Included Files

### `amazon_ip_ranges.txt`

A plain-text list of all current AWS IPv4 and IPv6 address ranges.
Each line contains a single CIDR block, making it easy to use in firewalls, network configurations, or IP filtering tools.

### `amazon_ip_ranges.mrs`

A **Mihomo Rule Set (MRS)** version of the AWS IP ranges.
Optimized for use with **Clash**, **Mihomo**, and other compatible clients — ideal for creating rules that match AWS traffic.

## ⚙️ Source & Update

All data is automatically fetched and parsed from:

```
https://ip-ranges.amazonaws.com/ip-ranges.json
```

This ensures you always have the **latest and most accurate AWS IP ranges** available.

🕛 **Update Schedule:**
The repository is automatically updated **every day at 00:00 (GMT+3)** to keep all data fresh and synchronized with the latest AWS IP announcements.

## 💡 Example Usage

### Mihomo / Clash Configuration:

```yaml
rule-providers:
  aws:
    type: http
    behavior: ipcidr
    path: ./rules/amazon_ip_ranges.mrs
    url: https://github.com/pius-pp/amazon_ip_ranges/raw/refs/heads/main/amazon_ip_ranges.mrs
    interval: 24h
```

## ⏰ Generation

The `.txt` and `.mrs` files are automatically generated from the JSON source using a custom parser script.
They can be scheduled for updates (e.g., via cron) to ensure up-to-date IP coverage at all times.
