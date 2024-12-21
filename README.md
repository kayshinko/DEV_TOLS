# 🌟 DigiPay - Open Source PPOB Platform

<div align="center">

![DigiPay Logo](https://avatars.githubusercontent.com/u/166167053?v=4&size=64)

[![Laravel](https://img.shields.io/badge/Laravel-v10.0-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)](https://laravel.com)
[![Vue.js](https://img.shields.io/badge/Vue.js-v3.0-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org)
[![MySQL](https://img.shields.io/badge/MySQL-v8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)

### 💫 Platform PPOB Open Source dengan Integrasi Multi Provider
*Solusi Pembayaran Digital Terbuka untuk Semua*

[Demo](https://demo.digipay.com) • [Documentation](https://docs.digipay.com) • [Community](https://github.com/kayshinko/DEV_TOLS/discussions)

</div>

## ⚡ Fitur Utama

<div align="center">

🔒 **Multi Provider** | 📱 **Multi Gateway** | ⚡ **Open Source** | 💰 **Scalable**

</div>

### 🎯 Produk Digital (Digiflazz)

- 📱 **Pulsa & Data**
  - All Operator (Telkomsel, XL, Indosat, dll)
  - Paket Data Internet
  - Paket Telepon & SMS
  
- 💡 **Pembayaran Tagihan**
  - Token PLN & Tagihan Listrik
  - PDAM
  - BPJS Kesehatan
  - Internet & TV Kabel
  
- 🎮 **Voucher Digital**
  - Mobile Legends
  - PUBG Mobile
  - Free Fire
  - Steam Wallet
  - Google Play
  - Apple iTunes

### 💳 Payment Gateway Integration

- 🏧 **Tripay**
  - Virtual Account
  - QRIS
  - E-Wallet
  - Retail Outlet
  
- 💸 **Xendit**
  - Virtual Account
  - Credit Card
  - E-Wallet
  - Direct Debit
  
- 💰 **Midtrans**
  - Bank Transfer
  - Credit Card
  - E-Wallet
  - Convenience Store

## 🛠️ Tech Stack & Integration

### Core Technology
- Laravel 10.x
- Vue.js 3
- Tailwind CSS
- MySQL
- Redis

### Provider Integration
```php
// Digiflazz Configuration
DIGIFLAZZ_USERNAME=username
DIGIFLAZZ_API_KEY=api-key
DIGIFLAZZ_URL=https://api.digiflazz.com/v1

// Payment Gateway Keys
TRIPAY_API_KEY=your-api-key
TRIPAY_PRIVATE_KEY=your-private-key
TRIPAY_MERCHANT_CODE=your-merchant-code

XENDIT_SECRET_KEY=your-secret-key
XENDIT_PUBLIC_KEY=your-public-key

MIDTRANS_SERVER_KEY=your-server-key
MIDTRANS_CLIENT_KEY=your-client-key
MIDTRANS_MERCHANT_ID=your-merchant-id
```

## ⚙️ Instalasi

### Prerequisites
```bash
node >= 16.0.0
php >= 8.1
composer
mysql >= 8.0
redis
```

### 🚀 Quick Start

1. **Clone Repository**
```bash
git clone https://github.com/kayshinko/DEV_TOLS.git
cd digipay
```

2. **Setup Backend**
```bash
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate --seed
```

3. **Setup Frontend**
```bash
npm install
npm run build
```

4. **Provider Configuration**

Edit `.env` dan sesuaikan kredensial provider:
```env
# Core Application
APP_NAME=DigiPay
APP_ENV=local
APP_URL=http://localhost:8000

# Database
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=digipay
DB_USERNAME=root
DB_PASSWORD=

# Redis Cache
REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

# Digiflazz
DIGIFLAZZ_USERNAME=
DIGIFLAZZ_API_KEY=
DIGIFLAZZ_URL=

# Tripay
TRIPAY_API_KEY=
TRIPAY_PRIVATE_KEY=
TRIPAY_MERCHANT_CODE=

# Xendit
XENDIT_SECRET_KEY=
XENDIT_PUBLIC_KEY=

# Midtrans
MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
MIDTRANS_MERCHANT_ID=
```

## 📚 API Integration

### Digiflazz Integration
```php
// Check Balance
$response = Http::post('https://api.digiflazz.com/v1/cek-saldo', [
    'cmd' => 'deposit',
    'username' => env('DIGIFLAZZ_USERNAME'),
    'sign' => md5(env('DIGIFLAZZ_USERNAME') . env('DIGIFLAZZ_API_KEY') . 'depo')
]);

// Price List
$response = Http::post('https://api.digiflazz.com/v1/price-list', [
    'cmd' => 'prepaid',
    'username' => env('DIGIFLAZZ_USERNAME'),
    'sign' => md5(env('DIGIFLAZZ_USERNAME') . env('DIGIFLAZZ_API_KEY') . 'pricelist')
]);
```

### Payment Gateway Integration

```php
// Tripay Payment
$payload = [
    'method'            => 'BRIVA',
    'merchant_ref'      => $order_id,
    'amount'            => $amount,
    'customer_name'     => $customer_name,
    'customer_email'    => $customer_email,
    'customer_phone'    => $customer_phone,
    'order_items'       => $items,
    'expired_time'      => (time() + (24 * 60 * 60)), // 24 jam
    'signature'         => hash_hmac('sha256', $merchant_code.$order_id.$amount, $private_key)
];

// Xendit Payment
\Xendit\Xendit::setApiKey(env('XENDIT_SECRET_KEY'));
$params = [ 
    'external_id' => $order_id,
    'amount' => $amount,
    'bank_code' => 'BRI',
    'name' => $customer_name,
    'is_closed' => true,
    'expiration_date' => date('Y-m-d H:i:s', strtotime('+1 day'))
];

// Midtrans Payment
\Midtrans\Config::$serverKey = env('MIDTRANS_SERVER_KEY');
\Midtrans\Config::$isProduction = false;
\Midtrans\Config::$isSanitized = true;
\Midtrans\Config::$is3ds = true;
```

## 🔒 Security Features

- 🔐 Provider API Signature
- 🛡️ Payment Gateway Encryption
- 📝 Transaction Logging
- 🔍 IP Whitelisting
- 🔒 Rate Limiting

## 📈 Roadmap

- [x] Digiflazz Integration
- [x] Multi Payment Gateway
- [x] Transaction Logging
- [ ] Webhook Handler
- [ ] Mobile App
- [ ] API Documentation
- [ ] Multi Provider Support

## 👥 Tim Pengembang

- **Project Lead** - [SmilanS](https://github.com/kayshinko)
- **Backend Developer** - [SmilanS](https://github.com/kayshinko)
- **Frontend Developer** - [SmilanS](https://github.com/kayshinko)
- **UI/UX Designer** - [SmilanS](https://github.com/kayshinko)

## 🤝 Contributing

Kami menerima kontribusi dari komunitas! Silakan:

1. Fork repository
2. Buat feature branch
3. Commit perubahan
4. Push ke branch
5. Submit pull request

## 📝 License

Project ini dilisensikan di bawah MIT License. Lihat [LICENSE](LICENSE) untuk detail.

---

<div align="center">

### ⭐ Beri bintang jika project ini membantu!

[Report Bug](https://github.com/kayshinko/DEV_TOLS/issues) • [Request Feature](https://github.com/kayshinko/DEV_TOLS/issues)

Made with ❤️ by SmilanS Team

</div>
