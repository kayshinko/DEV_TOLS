# 🌟 DigiPay - Platform PPOB Modern

<div align="center">

![DigiPay Logo](https://raw.githubusercontent.com/username/digipay/main/public/logo.png)

[![Laravel](https://img.shields.io/badge/Laravel-v10.0-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)](https://laravel.com)
[![Vue.js](https://img.shields.io/badge/Vue.js-v3.0-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org)
[![MySQL](https://img.shields.io/badge/MySQL-v8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)

### 💫 Platform PPOB Modern untuk Semua Kebutuhan Digital
*Solusi Pembayaran Digital Terlengkap*

[Live Demo](https://demo.digipay.com) • [API Docs](https://api.digipay.com) • [Report Bug](https://github.com/username/digipay/issues)

</div>

## ⚡ Fitur Utama

<div align="center">

🔒 **Secure Payment** | 📱 **Multi-Platform** | ⚡ **Real-time Transaction** | 💰 **Multi-Wallet**

</div>

### 🎯 Produk & Layanan

- 📱 **Pulsa & Paket Data**
  - All Operator
  - Paket Internet
  - Paket Telepon
  
- 💡 **Tagihan & Pembayaran**
  - Listrik PLN
  - PDAM
  - BPJS
  - PGN
  
- 📺 **TV Berlangganan**
  - Indihome
  - First Media
  - MNC Vision
  
- 🎮 **Voucher Game**
  - Mobile Legends
  - PUBG Mobile
  - Free Fire
  - Genshin Impact

### 💼 Fitur Bisnis

- 👥 **Multi-level Marketing**
  - Sistem Referral
  - Komisi Berjenjang
  - Tracking Downline
  
- 📊 **Laporan & Analitik**
  - Laporan Transaksi
  - Analisis Penjualan
  - Performa Agen
  
- 💳 **Sistem Pembayaran**
  - Virtual Account
  - E-Wallet Integration
  - Direct Transfer

## 🛠️ Tech Stack

### Frontend
- Vue.js 3
- Tailwind CSS
- Vuex for State Management
- Vue Router
- Axios

### Backend
- Laravel 10
- MySQL Database
- Redis Cache
- JWT Authentication

### Payment Gateway Integration
- Midtrans
- Xendit
- DOKU

## ⚙️ Instalasi

### Prerequisites

```bash
node >= 16.0.0
php >= 8.1
composer
mysql >= 8.0
redis
```

### 🚀 Langkah Instalasi

1. **Clone Repository**
```bash
git clone https://github.com/username/digipay.git
cd digipay
```

2. **Setup Backend**
```bash
# Install dependencies
composer install

# Setup environment
cp .env.example .env
php artisan key:generate

# Migrate database
php artisan migrate --seed

# Install Passport
php artisan passport:install
```

3. **Setup Frontend**
```bash
# Install dependencies
npm install

# Build assets
npm run build
```

4. **Konfigurasi Environment**

Sesuaikan file `.env`:
```env
APP_NAME=DigiPay
APP_ENV=local
APP_URL=http://localhost:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=digipay
DB_USERNAME=root
DB_PASSWORD=

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MIDTRANS_SERVER_KEY=your-server-key
MIDTRANS_CLIENT_KEY=your-client-key
MIDTRANS_MERCHANT_ID=your-merchant-id

XENDIT_SECRET_KEY=your-secret-key
XENDIT_PUBLIC_KEY=your-public-key
```

5. **Jalankan Aplikasi**
```bash
# Terminal 1: Laravel Server
php artisan serve

# Terminal 2: Vite Dev Server
npm run dev
```

## 📱 Screenshot Aplikasi

<div align="center">

| Dashboard Admin | Transaksi |
|----------------|-----------|
| ![Dashboard](screenshots/dashboard.png) | ![Transactions](screenshots/transactions.png) |

| Mobile View | Report Analytics |
|-------------|-----------------|
| ![Mobile](screenshots/mobile.png) | ![Analytics](screenshots/analytics.png) |

</div>

## 📚 API Documentation

API documentation tersedia di `/api/documentation`. Generate dengan:

```bash
php artisan l5-swagger:generate
```

## 🔒 Security Features

- 🔐 2FA Authentication
- 🛡️ Anti-Fraud System
- 📝 Transaction Logging
- 🔍 IP Whitelisting
- 🔒 End-to-end Encryption

## 🚀 Production Deployment

1. **Optimize Laravel**
```bash
composer install --optimize-autoloader --no-dev
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

2. **Build Frontend**
```bash
npm run build
```

3. **Setup Supervisor**
```bash
[program:digipay-worker]
process_name=%(program_name)s_%(process_num)02d
command=php /path/to/project/artisan queue:work
autostart=true
autorestart=true
user=www-data
numprocs=8
redirect_stderr=true
stdout_logfile=/path/to/project/worker.log
```

## 📈 Roadmap

- [x] Multi-payment Gateway
- [x] Sistem Referral
- [x] Real-time Notification
- [ ] Mobile App Integration
- [ ] Cryptocurrency Payment
- [ ] International Remittance

## 👥 Tim Pengembang

- **Project Manager** - [SmilanS](https://github.com/pmname)
- **Backend Developer** - [SmilanS](https://github.com/backenddev)
- **Frontend Developer** - [SmilanS](https://github.com/frontenddev)
- **UI/UX Designer** - [SmilanS](https://github.com/designer)

## 🤝 Contributing

Kontribusi selalu diterima!

1. Fork project ini
2. Buat feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit perubahan (`git commit -m 'Add Amazing Feature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buka Pull Request

## 📝 License

Project ini dilisensikan di bawah MIT License - lihat file [LICENSE](LICENSE) untuk detail.

---

<div align="center">

### ⭐ Beri bintang jika project ini membantu!

[Report Bug](https://github.com/username/digipay/issues) • [Request Feature](https://github.com/username/digipay/issues)

</div>

## 📊 Project Status

![Alt](https://repobeats.axiom.co/api/embed/your-repository-id.svg "Repobeats analytics image")

---

<div align="center">
Made with ❤️ by SmilanS Team
</div>
