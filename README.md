# Linea Terra — Website (offline mirror, sudah dibersihkan total)

Salinan offline dari `https://heronaiapp.com/` yang sudah di-rebrand **penuh menjadi Linea Terra**
(jasa desain arsitektur, interior & kontraktor — bahasa Indonesia). Semua jejak brand lama
(teks, logo, link, gambar, nama file, analytics) sudah dihapus.

## Isi

```
heronaiapp.com/
├── index.html                       → halaman utama (semua URL diarahkan ke file lokal)
├── logo-mark.png / logo-lt.png      → logo asli Linea Terra (emblem transparan & versi square)
├── favicon.png / og-image.jpg       → ikon tab & gambar share sosial media (dari logo asli)
├── cdn.prod.website-files.com/      → asset (struktur folder asli dipertahankan)
│   ├── 6a4b5161f0d11f1602cc3bbf/    → gambar, font (BTGrotesk, Geist Mono),
│   │                                   css/linea-terra.webflow.min.css, js webflow
│   ├── 6a4b5161f0d11f1602cc3bc0/    → logo partner + foto audiens
│   └── 68f73a0fbae6fa626a19135c/    → background SVG/PNG hero
└── libs/                            → library & script situs (jquery, gsap, swiper, lenis,
                                        barba, main.js, MeetingsEmbedCode.js)
```

## Cara pakai

```bash
cd heronaiapp.com
python -m http.server 8080
# buka http://localhost:8080
```

## Catatan teknis

- Cookie banner memakai id `linea-cookie-root` (konsisten di index.html dan libs/main.js).
- `main.js` dimuat langsung sebagai `<script type="module">` di akhir body (loader terpisah
  dihapus karena membuat inisialisasi melewatkan event `DOMContentLoaded`).
- Seluruh situs berjalan offline — tidak ada lagi dependensi jaringan (analytics & loader
  remote dihapus).
- Logo header/footer/favicon/OG image memakai logo asli Linea Terra (emblem lingkaran:
  gedung + bukit terakota), diekstrak dari file logo resmi. Asset gambar ilustrasi tetap
  milik desain asli dan bisa ditukar dengan foto proyek Linea Terra kapan saja.
- Kode sumber lama (webflow) direferensikan dengan nama file yang sudah diubah
  (css/linea-terra.webflow.min.css, linea-terra-full.jpg).
