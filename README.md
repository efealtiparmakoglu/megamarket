# 🛒 MegaMarket - Çok Satıcılı E-Ticaret Pazaryeri

[![Next.js](https://img.shields.io/badge/Next.js-14.0+-000000?logo=next.js)](https://nextjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18.0+-339933?logo=node.js)](https://nodejs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169E1?logo=postgresql)](https://postgresql.org/)
[![Redis](https://img.shields.io/badge/Redis-7.0+-DC382D?logo=redis)](https://redis.io/)
[![Elasticsearch](https://img.shields.io/badge/Elasticsearch-8.0+-005571?logo=elasticsearch)](https://elastic.co/)

🚀 **MegaMarket**, Amazon ve Hepsiburada'dan ilham alınmış, çok satıcılı, ölçeklenebilir bir e-ticaret pazaryeri platformudur.

## ✨ Ana Özellikler

### 🏪 Çok Satıcılı Yapı
- 👤 **Satıcı Paneli** - Bağımsız satıcı yönetimi
- 📦 **Stok Senkronizasyonu** - Gerçek zamanlı stok takibi
- 💰 **Komisyon Sistemi** - Otomatik komisyon hesaplama
- 📊 **Satıcı Analitikleri** - Detaylı satış raporları

### 🔍 Akıllı Arama
- 🔎 **Elasticsearch** - Yıldırım hızında arama
- 🎯 **Filtreleme** - Çok boyutlu filtreler
- 💡 **Otomatik Tamamlama** - Akıllı öneriler
- 🔥 **Popüler Aramalar** - Trend ürünler

### 🛒 Alışveriş Deneyimi
- 🛍️ **Akıllı Sepet** - Dinamik fiyatlandırma
- 💳 **Çoklu Ödeme** - Kredi kartı, havale, kapıda ödeme
- 🎫 **İndirim Kuponları** - Promosyon yönetimi
- 📱 **Responsive Tasarım** - Mobil öncelikli

## 🛠️ Teknoloji Stack

| Katman | Teknolojiler |
|--------|-------------|
| **Frontend** | Next.js 14, React 18, Tailwind CSS, Redux Toolkit |
| **Backend** | Node.js, Express.js, TypeScript |
| **Database** | PostgreSQL (Primary), MongoDB (Logs), Redis (Cache) |
| **Search** | Elasticsearch, Algolia |
| **Storage** | AWS S3, CloudFront CDN |
| **Payment** | Stripe, Iyzico |
| **Message Queue** | RabbitMQ, Bull Queue |
| **Monitoring** | Prometheus, Grafana, Sentry |

## 🚀 Kurulum

### Gereksinimler
- Node.js 18+
- PostgreSQL 15+
- MongoDB 6+
- Redis 7+
- Elasticsearch 8+

### Hızlı Başlangıç
```bash
# Repoyu klonla
git clone https://github.com/efealtiparmakoglu/megamarket.git
cd megamarket

# Bağımlılıkları yükle
npm install
cd client && npm install && cd ..

# Ortam değişkenlerini ayarla
cp .env.example .env
# .env dosyasını düzenle

# Veritabanını oluştur
npm run db:create
npm run db:migrate
npm run db:seed

# Geliştirme sunucusunu başlat
npm run dev
```

## 📁 Proje Yapısı

```
megamarket/
├── 📁 client/                    # Next.js Frontend
│   ├── 📁 src/
│   │   ├── 📁 app/               # App Router
│   │   ├── 📁 components/        # React Components
│   │   ├── 📁 lib/               # Utils & Hooks
│   │   └── 📁 store/             # Redux Store
│   └── package.json
├── 📁 server/                    # Express Backend
│   ├── 📁 src/
│   │   ├── 📁 config/            # Configuration
│   │   ├── 📁 modules/           # Feature Modules
│   │   │   ├── 📁 auth/          # Authentication
│   │   │   ├── 📁 products/      # Product Management
│   │   │   ├── 📁 orders/        # Order Processing
│   │   │   └── 📁 vendors/       # Vendor Management
│   │   ├── 📁 shared/            # Shared Resources
│   │   └── 📁 jobs/              # Background Jobs
│   └── package.json
├── 📁 shared/                    # Shared Types & Utils
└── 📄 docker-compose.yml
```

## 🔌 API Dokümantasyonu

### Ürünler
```http
GET    /api/v1/products          # Ürün listesi
GET    /api/v1/products/:id      # Ürün detayı
POST   /api/v1/products          # Yeni ürün (Vendor)
PUT    /api/v1/products/:id      # Ürün güncelle
DELETE /api/v1/products/:id      # Ürün sil
```

### Sepet
```http
GET    /api/v1/cart              # Sepetim
POST   /api/v1/cart/items        # Sepete ekle
PUT    /api/v1/cart/items/:id    # Miktar güncelle
DELETE /api/v1/cart/items/:id    # Sepetten çıkar
```

### Siparişler
```http
POST   /api/v1/orders            # Sipariş oluştur
GET    /api/v1/orders            # Siparişlerim
GET    /api/v1/orders/:id        # Sipariş detayı
PUT    /api/v1/orders/:id/cancel # Sipariş iptal
```

## 🎯 SEO Optimizasyonları

- ✅ **SSR/SSG** - Next.js ile sunucu taraflı render
- ✅ **Dynamic Meta Tags** - Ürün bazlı meta açıklamalar
- ✅ **Structured Data** - JSON-LD Schema markup
- ✅ **XML Sitemap** - Otomatik site haritası
- ✅ ** robots.txt** - Arama motoru yönetimi
- ✅ **Core Web Vitals** - LCP, FID, CLS optimizasyonu
- ✅ **Canonical URLs** - Yinelenen içerik önleme
- ✅ **Open Graph** - Sosyal medya entegrasyonu

## 🔒 Güvenlik Özellikleri

- 🔐 **JWT + Refresh Token** - Güvenli kimlik doğrulama
- 🛡️ **Helmet.js** - HTTP header güvenliği
- 🚦 **Rate Limiting** - API koruma (100 req/15dk)
- 📝 **Joi Validation** - Input sanitization
- 🔒 **SQL Injection Protection** - Prepared statements
- 🛡️ **XSS Protection** - Content Security Policy
- 🔐 **Stripe PCI Compliance** - Ödeme güvenliği

## 📊 Performans Metrikleri

- ⚡ **TTFB**: < 100ms
- 📱 **Lighthouse Score**: 95+
- 🔍 **Search API**: < 50ms
- 🛒 **Checkout**: < 2s
- 🖼️ **Image Load**: WebP/AVIF format
- 📦 **Bundle Size**: < 200KB (initial)

## 🧪 Test

```bash
# Unit tests
npm run test:unit

# Integration tests
npm run test:integration

# E2E tests
npm run test:e2e

# Load tests
npm run test:load
```

## 🚀 Deployment

### Docker Compose
```bash
docker-compose -f docker-compose.prod.yml up -d
```

### Kubernetes
```bash
kubectl apply -f k8s/
```

## 📈 Monitoring

- 📊 **Grafana Dashboard** - Real-time metrics
- 🔔 **Alert Manager** - Anomaly detection
- 📜 **ELK Stack** - Centralized logging
- 🐛 **Sentry** - Error tracking

## 🌟 Özellikler Yol Haritası

- [ ] 🤖 AI Öneri Sistemi
- [ ] 🌍 Çok Dil Desteği
- [ ] 📱 Native Mobil Uygulamalar
- [ ] 🔗 Blockchain Ödeme
- [ ] 🎙️ Sesli Arama
- [ ] 🤳 AR Ürün Görüntüleme

## 📞 İletişim

**Efe Altıparmakoğlu**
- 📧 efealtiparmakoglu@hotmail.com
- 💼 [LinkedIn](https://linkedin.com/in/efealtiparmakoglu)
- 🐦 [Twitter](https://twitter.com/efealtiparmak)

---

⭐ **Projeyi beğendiyseniz star atmayı unutmayın!**