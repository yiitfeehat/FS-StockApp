# Stock Management API 📈

![Stock Management API](./StockAPI.gif)
### ERD:

![ERD](./erdStockAPI.png)

### ERD-2 (snake_case):

![ERD](./erdStockAPI2.png)

Bu proje, stok takip ve yönetim süreçlerini dijitalleştirmek için geliştirilmiş, kapsamlı ve ölçeklenebilir bir **MERN Stack** (MongoDB, Express, React, Node.js) uygulamasıdır. Hem backend API hem de modern bir frontend arayüzü sunarak, firmaların ürün, satış, satın alma ve marka yönetimini tek bir platformdan yapmasını sağlar.

## 🌟 Özellikler

*   **Yetkilendirme & Kimlik Doğrulama (Auth):** JWT (JSON Web Token) tabanlı güvenli giriş/kayıt sistemi, Access & Refresh Token yapısı.
*   **Dashboard:** Satışlar, satın almalar ve toplam kar/zarar durumunu özetleyen, `Tremor` grafik kütüphanesi ile güçlendirilmiş interaktif panel.
*   **Stok Yönetimi:** Ürünlerin stok miktarlarını, kategorilerini ve markalarını detaylı takip etme.
*   **Satış & Satın Alma:** Dinamik stok güncellemesi yapan satış ve satın alma işlemleri.
*   **Firma & Marka Yönetimi:** Tedarikçi firmaların ve ürün markalarının kayıt altına alınması.
*   **Gelişmiş Filtreleme & Arama:** Backend tarafında `search`, `sort`, `pagination` ve `filter` yetenekleri.
*   **Dokümantasyon:** Swagger UI ve Redoc ile otomatik oluşturulan güncel API dokümantasyonu.
*   **Modern Frontend:** React, Vite, Redux Toolkit, TailwindCSS ve Material UI kullanılarak geliştirilmiş responsive arayüz.

## 🛠 Kullanılan Teknolojiler ve Yöntemler

### Backend
*   **Core:** Node.js, Express.js
*   **Database:** MongoDB, Mongoose (ORM)
*   **Authentication:** `jsonwebtoken` (JWT), `pbkdf2` (Password Hashing)
*   **Documentation:** `swagger-autogen`, `swagger-ui-express`, `redoc-express`
*   **Middleware:** `cors` (Security), Custom Error & Query Handlers
*   **Utility:** `dotenv` (Environment Config)

### Frontend
*   **Core:** React.js, Vite
*   **State Management:** Redux Toolkit, Redux Persist
*   **Styling:** TailwindCSS, Material UI (MUI)
*   **Charts:** Tremor React
*   **HTTP Client:** Axios
*   **Routing:** React Router DOM

## 📂 Proje Yapısı

```
/
├── client/             # Frontend React Uygulaması
│   ├── src/
│   │   ├── app/        # Redux store konfigürasyonu
│   │   ├── components/ # Reusable UI bileşenleri (Charts, KpiCard, vb.)
│   │   ├── features/   # Redux slice'ları (auth, stock)
│   │   ├── hook/       # Custom React Hooks (useAxios, useStockCall)
│   │   ├── pages/      # Uygulama sayfaları (Dashboard, Firms, Products...)
│   │   └── router/     # Sayfa yönlendirmeleri
│   └── ...
├── src/                # Backend Node.js Uygulaması
│   ├── configs/        # Veritabanı bağlantı ayarları
│   ├── controllers/    # Request/Response mantığı (Auth, Brand, Firm, Product...)
│   ├── middlewares/    # Ara yazılımlar (Auth, Permissions, QueryHandler)
│   ├── models/         # Mongoose şemaları ve veritabanı modelleri
│   ├── routes/         # API endpoint tanımları
│   └── helpers/        # Yardımcı fonksiyonlar (Password Encrypt, Sync)
├── index.js            # Backend giriş noktası
├── swaggerAutogen.js   # Dokümantasyon oluşturma scripti
└── .env                # Çevresel değişkenler
```

## 🚀 Kurulum

Proje hem backend hem frontend içerir. Her ikisinin de bağımlılıkları yüklenmelidir.

1.  Projeyi indirin (Clone).
2.  Terminali açın ve proje dizinine gidin.
3.  Backend kurulumu:
    ```bash
    npm install
    # Development için nodemon önerilir:
    npm install -D nodemon
    ```
4.  Frontend kurulumu:
    ```bash
    cd client
    npm install
    ```
5.  Ana dizinde `.env` dosyasını oluşturun:
    ```env
    HOST=127.0.0.1
    PORT=8000
    MONGODB=mongodb+srv://... (Connection String)
    ACCESS_KEY=...
    REFRESH_KEY=...
    SECRET_KEY=...
    CORS_ORIGIN=*
    ```
6.  `client` dizininde `.env` dosyasını oluşturun:
    ```env
    VITE_BASE_URL=http://127.0.0.1:8000/api/v1/
    ```
7.  Uygulamayı başlatın:
    *   **Backend:** Ana dizinde `npm start`
    *   **Frontend:** `client` dizininde `npm run dev` (Geliştirme modu) veya `npm run build` (Production build)

8.  API Dokümantasyonuna erişim için tarayıcınızda:
    *   **Swagger:** `http://localhost:8000/documents/swagger`
    *   **Redoc:** `http://localhost:8000/documents/redoc`
    *   **JSON:** `http://localhost:8000/documents/json`
