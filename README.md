# 🖥️ NexusDev — Company Profile Website

Landing page resmi **NexusDev**, perusahaan IT yang bergerak di bidang pengembangan website, aplikasi CRM, ERP, POS, dan solusi digital lainnya.

---

## 🚀 Tech Stack

- **HTML5** — struktur halaman
- **CSS3** — styling & animasi
- **Vanilla JS** — interaksi ringan (filter portfolio, smooth scroll)
- **Google Fonts** — Plus Jakarta Sans
- **Tabler Icons** — icon library

---

## 📁 Struktur Folder

```
nexusdev-website/
├── index.html          # Halaman utama
├── assets/
│   ├── images/         # Gambar & foto
│   └── favicon.ico     # Favicon
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Actions CI/CD
└── README.md
```

---

## 🌐 Sections

- **Hero** — tagline utama & statistik perusahaan
- **Services** — layanan: Website, CRM, ERP, POS, Mobile App, DevOps
- **Pricing** — paket harga: Starter, Business, Enterprise
- **Portfolio** — galeri proyek dengan filter kategori
- **Contact** — WhatsApp, email, dan info kontak

---

## ⚙️ Deployment

Website ini di-deploy otomatis ke VPS via **GitHub Actions** setiap kali ada push ke branch `main`.

### Setup awal di VPS

```bash
cd /var/www/nexusdev
git init
git remote add origin https://github.com/username/nexusdev-website.git
git pull origin main
```

### Nginx config

```nginx
server {
    listen 80;
    server_name nexusdev.id www.nexusdev.id;

    root /var/www/nexusdev;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }

    gzip on;
    gzip_types text/css application/javascript image/svg+xml;
}
```

### GitHub Secrets yang diperlukan

| Secret | Keterangan |
|---|---|
| `SSH_PRIVATE_KEY` | Private key untuk akses VPS |
| `SSH_HOST` | IP address VPS |
| `SSH_USER` | Username VPS (misal: `ubuntu`) |

---

## 🔧 Development Lokal

Tidak perlu build step — cukup buka langsung di browser:

```bash
# Clone repo
git clone https://github.com/username/nexusdev-website.git

# Buka di browser
open index.html
# atau klik 2x file index.html
```

---

## 📦 Deploy Manual

```bash
scp index.html user@IP_VPS:/var/www/nexusdev/
```

---

## 📄 Lisensi

© 2025 NexusDev. All rights reserved.
