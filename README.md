# CVLolos.ai — AI-Powered CV Builder Indonesia

## 🚀 Deploy ke Vercel

### Cara 1: Vercel CLI
```bash
npm install -g vercel
vercel
```

### Cara 2: GitHub + Vercel Dashboard
1. Push repo ke GitHub
2. Buka [vercel.com](https://vercel.com) → Import Project
3. Pilih repo ini → Deploy

### Cara 3: Drag & Drop (setelah build)
```bash
npm install
npm run build
```
Upload folder `dist/` ke Vercel Dashboard

## ⚙️ Konfigurasi Penting

Edit `src/App.jsx` untuk mengubah:
- **BANK** — Info rekening tujuan pembayaran
- **PLANS** — Harga paket PRO dan Lifetime

## 🔑 API Key Anthropic

Fitur AI (ATS Checker, Cover Letter, Career Guidance) membutuhkan Anthropic API Key.

Tambahkan di Vercel Dashboard → Settings → Environment Variables:
```
VITE_ANTHROPIC_API_KEY=sk-ant-xxxxx
```

Kemudian update fetch di App.jsx:
```js
headers: {
  "x-api-key": import.meta.env.VITE_ANTHROPIC_API_KEY,
  "anthropic-version": "2023-06-01",
  "Content-Type": "application/json",
}
```

> ⚠️ **Penting:** Jangan expose API key langsung di frontend untuk production.
> Gunakan Vercel Serverless Functions sebagai proxy.

## 📁 Struktur Project
```
cvlolos/
├── src/
│   ├── App.jsx      ← Seluruh kode aplikasi
│   ├── main.jsx     ← Entry point React
│   └── index.css    ← Tailwind CSS
├── index.html
├── package.json
├── vite.config.js
├── tailwind.config.js
└── vercel.json
```

## 👤 Demo Login
- **Admin:** admin@cvlolos.ai / admin123
