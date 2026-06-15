در اینجا یک فایل README.md حرفه‌ای، کامل و با قابلیت انتخاب زبان انگلیسی/فارسی برای پروژه شما آماده شده است:

```markdown
<div align="center">
  
# 🚀 Arista VPN Config Aggregator

**Professional & Automated VPN Configuration Aggregation System**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/yourusername/yourrepo/main.yml?branch=main)](https://github.com/yourusername/yourrepo/actions)
[![Last Update](https://img.shields.io/github/last-commit/yourusername/yourrepo)](https://github.com/yourusername/yourrepo)

**[English](#english) | [فارسی](#persian)**

</div>

---

<a name="english"></a>
## 🇬🇧 English Documentation

### 📖 About The Project

**Arista Config Aggregator** is a fully automated, enterprise-grade system that collects, validates, categorizes, and deduplicates VPN configurations from hundreds of Telegram channels and GitHub repositories. The system runs every 6 hours via GitHub Actions, ensuring you always have access to fresh, working configurations.

### ⚙️ How It Works

The system consists of four core modules working in harmony:

#### 1. 🤖 Telegram Channel Extractor
- Scrapes **500+ Telegram channels** for VPN configurations
- Implements **intelligent dead channel detection** - channels with no new posts for 2+ days are suspended for 7 days
- **Permanent blacklisting** for consistently dead channels
- Extracts only the latest 15 configs per channel to avoid stale content
- Supports protocols: VMess, VLESS, Trojan, Shadowsocks, Hysteria2, Hysteria, TUIC, WireGuard

#### 2. 🐙 GitHub Repository Extractor
- Fetches configurations from 10+ curated GitHub sources
- Handles raw files, CDN mirrors, and GitVerse repositories

#### 3. 🔄 Config Combiner & Tiering System
- **Smart deduplication** using MD5 hashing
- **Protocol categorization** (vmess, vless, trojan, ss, hysteria2, hysteria, tuic, wireguard, other)
- **Tiered output system** with overlapping: 50, 100, 150, 200, 250, 300, 400, 500, and ALL configs
- Each tier includes a 10% overlap from previous tier for seamless rotation

#### 4. 🧹 Validation & Standardization
- All configurations are validated for proper formatting
- Shadowsocks URLs are standardized across different formats
- VMess JSON structures are verified (port range, UUID format)

### 📊 Output Structure

```

configs/
├── telegram/           # Configs from Telegram channels
│   ├── vmess/
│   ├── vless/
│   ├── trojan/
│   └── ... (50/100/150... tier files)
├── github/            # Configs from GitHub sources
│   └── ... (same tiered structure)
└── combined/          # Merged & deduplicated from both sources
└── ... (complete tiered structure)

```

### 🔗 Subscription & Community

> ⚠️ **Important**: Direct subscription links are NOT provided on GitHub for security and stability reasons.

### 📡 Join Our Telegram Channel: [@aristapanel](https://t.me/aristapanel)

#### What You Get in the Telegram Channel:

| Service | Description |
|---------|-------------|
| **Subscription Links** | Direct subscription URLs for this aggregation system |
| **Telegram Proxies** | MTProto and SOCKS5 proxies for Telegram access |
| **Clean IPs** | Scanned from hundreds of millions of IPs - optimized for streaming & browsing |
| **Daily Updates** | Fresh configurations every 6 hours automatically |
| **Premium Support** | Direct support for configuration issues |

### 🌐 Public Control Panel

Access our **Cloudflare Workers-based public panel** for personal configuration optimization:

➡️ **[https://arista-panel.arista-panel.workers.dev/](https://arista-panel.arista-panel.workers.dev/)**

Features:
- Personalize your configurations
- Filter by protocol and region
- Generate custom subscription links
- Optimize for your specific use case

### 🛠️ Technical Specifications

- **Update Frequency**: Every 6 hours (cron: `0 */6 * * *`)
- **Timeout Protection**: 45 minutes maximum runtime
- **Smart Delays**: Random delays between requests to avoid rate limiting
- **Cache System**: Persistent JSON-based caching for dead channels
- **Version Support**: Python 3.14

### 📈 Statistics (per update cycle)

- **Telegram Channels Processed**: 500+
- **Active Channels**: ~300-400 (dead channels filtered automatically)
- **GitHub Sources**: 10+
- **Total Configs Collected**: 2000-5000 (before deduplication)
- **Unique Configs After Dedup**: 500-1500
- **Tiered Files Generated**: 80+ files

### 🚀 Quick Start (For Development)

```bash
# Clone the repository
git clone https://github.com/yourusername/yourrepo.git
cd yourrepo

# Install dependencies
pip install requests beautifulsoup4

# Run extractors manually
python telegram_extractor.py
python github_extractor.py
python combine_configs.py
```

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

❤️ Support the Project

If you find this project useful, consider:

· ⭐ Starring the repository on GitHub
· 📢 Sharing the project with others
· 🤝 Contributing via pull requests

---

<a name="persian"></a>

🇮🇷 مستندات فارسی

📖 درباره پروژه

Arista Config Aggregator یک سیستم کاملاً خودکار و حرفه‌ای برای جمع‌آوری، اعتبارسنجی، دسته‌بندی و حذف کانفیگ‌های تکراری VPN از صدها کانال تلگرام و مخازن گیت‌هاب است. این سیستم هر ۶ ساعت یکبار از طریق GitHub Actions اجرا می‌شود و تضمین می‌کند که همیشه به کانفیگ‌های تازه و فعال دسترسی دارید.

⚙️ نحوه عملکرد

سیستم از چهار ماژول اصلی تشکیل شده است:

1. 🤖 استخراج‌کننده کانال‌های تلگرام

· اسکرپ بیش از ۵۰۰ کانال تلگرامی برای کانفیگ‌های VPN
· پیاده‌سازی تشخیص هوشمند کانال‌های مرده - کانال‌هایی که بیش از ۲ روز پست جدید ندارند به مدت ۷ روز تعلیق می‌شوند
· لیست سیاه دائمی برای کانال‌های همیشه مرده
· استخراج فقط ۱۵ کانفیگ آخر هر کانال برای جلوگیری از محتوای قدیمی
· پشتیبانی از پروتکل‌ها: VMess، VLESS، Trojan، Shadowsocks، Hysteria2، Hysteria، TUIC، WireGuard

2. 🐙 استخراج‌کننده مخازن گیت‌هاب

· دریافت کانفیگ‌ها از ۱۰+ منبع گیت‌هاب
· پشتیبانی از فایل‌های خام، آینه‌های CDN و مخازن GitVerse

3. 🔄 ترکیب‌کننده و سیستم طبقه‌بندی

· حذف هوشمند تکراری‌ها با استفاده از هش MD5
· دسته‌بندی بر اساس پروتکل (vmess, vless, trojan, ss, hysteria2, hysteria, tuic, wireguard, other)
· سیستم خروجی طبقه‌بندی شده با همپوشانی: ۵۰، ۱۰۰، ۱۵۰، ۲۰۰، ۲۵۰، ۳۰۰، ۴۰۰، ۵۰۰ و ALL
· هر طبقه شامل ۱۰٪ همپوشانی از طبقه قبلی برای چرخش روان

4. 🧹 اعتبارسنجی و استانداردسازی

· اعتبارسنجی تمام کانفیگ‌ها برای فرمت صحیح
· استانداردسازی URLهای Shadowsocks در فرمت‌های مختلف
· بررسی ساختار JSON پروتکل VMess (محدوده پورت، فرمت UUID)

📊 ساختار خروجی

```
configs/
├── telegram/           # کانفیگ‌های کانال‌های تلگرام
│   ├── vmess/
│   ├── vless/
│   ├── trojan/
│   └── ... (فایل‌های طبقه‌بندی ۵۰/۱۰۰/۱۵۰...)
├── github/            # کانفیگ‌های منابع گیت‌هاب
│   └── ... (ساختار طبقه‌بندی مشابه)
└── combined/          # ادغام و حذف تکراری از هر دو منبع
    └── ... (ساختار طبقه‌بندی کامل)
```

🔗 سابسکرایب و جامعه

⚠️ مهم: لینک‌های مستقیم سابسکرایب به دلایل امنیتی و پایداری در گیت‌هاب قرار داده نمی‌شوند.

📡 به کانال تلگرام ما بپیوندید: @aristapanel

آنچه در کانال تلگرام دریافت می‌کنید:

سرویس توضیحات
لینک‌های سابسکرایب آدرس‌های مستقیم سابسکرایب برای این سیستم جمع‌آوری
پروکسی‌های تلگرام پروکسی‌های MTProto و SOCKS5 برای دسترسی به تلگرام
آی‌پی‌های تمیز اسکن شده از صدها میلیون آی‌پی - بهینه برای استریم و مرور
به‌روزرسانی روزانه کانفیگ‌های تازه هر ۶ ساعت به صورت خودکار
پشتیبانی ویژه پشتیبانی مستقیم برای مشکلات کانفیگ

🌐 پنل کنترل عمومی

دسترسی به پنل عمومی مبتنی بر Cloudflare Workers برای بهینه‌سازی شخصی کانفیگ‌ها:

➡️ https://arista-panel.arista-panel.workers.dev/

ویژگی‌ها:

· شخصی‌سازی کانفیگ‌های شما
· فیلتر بر اساس پروتکل و منطقه
· تولید لینک‌های سابسکرایب سفارشی
· بهینه‌سازی برای استفاده خاص شما

🛠️ مشخصات فنی

· فرکانس به‌روزرسانی: هر ۶ ساعت (cron: 0 */6 * * *)
· محافظت از Timeout: حداکثر ۴۵ دقیقه زمان اجرا
· تأخیرهای هوشمند: تأخیر تصادفی بین درخواست‌ها برای جلوگیری از محدودیت نرخ
· سیستم کش: کش پایدار مبتنی بر JSON برای کانال‌های مرده
· نسخه پایتون: 3.14

📈 آمار (در هر چرخه به‌روزرسانی)

· کانال‌های تلگرام پردازش شده: ۵۰۰+
· کانال‌های فعال: ~۳۰۰-۴۰۰ (کانال‌های مرده به طور خودکار فیلتر می‌شوند)
· منابع گیت‌هاب: ۱۰+
· کل کانفیگ‌های جمع‌آوری شده: ۲۰۰۰-۵۰۰۰ (قبل از حذف تکراری)
· کانفیگ‌های یکتا پس از حذف تکراری: ۵۰۰-۱۵۰۰
· فایل‌های طبقه‌بندی شده تولید شده: ۸۰+ فایل

🚀 شروع سریع (برای توسعه)

```bash
# کلون کردن مخزن
git clone https://github.com/yourusername/yourrepo.git
cd yourrepo

# نصب وابستگی‌ها
pip install requests beautifulsoup4

# اجرای دستی استخراج‌کننده‌ها
python telegram_extractor.py
python github_extractor.py
python combine_configs.py
```

📝 مجوز

این پروژه تحت مجوز MIT منتشر شده است - برای جزئیات بیشتر به فایل LICENSE مراجعه کنید.

❤️ حمایت از پروژه

اگر این پروژه برای شما مفید است، در نظر بگیرید:

· ⭐ ستاره دادن به مخزن در گیت‌هاب
· 📢 اشتراک‌گذاری پروژه با دیگران
· 🤝 مشارکت از طریق pull requestها

---

<div align="center">

Made with ❤️ by Arista Team (🇲‌🇲‌🇩‌)

</div>
```
