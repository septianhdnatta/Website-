# ASTRIONHUB — Web (Index V1/V2)

Landing page single-file bertema **AI Glass UI** dengan toggle tampilan **V1/V2**, section AI Chat (Yuuka), FAQ accordion, dan custom page-loader (Hinako). [file:590]

## Fitur Utama
- Toggle tampilan **V1 / V2** (state disimpan di `localStorage`). [file:590]
- Mobile menu + smooth scroll ke section (home / ai-chat / faq). [file:590]
- AI Chat “Yuuka” (V1 & V2 share histori chat yang sama di `localStorage`). [file:590]
- FAQ accordion (khusus V2). [file:590]
- Custom loader overlay saat pindah halaman (muncul ketika klik link, hilang saat page tampil). [file:590]

## Struktur File (contoh)
/
├─ index.html
└─ page/
├─ features.html
├─ demo.html
├─ contact.html
├─ snipsets.html
└─ 404.html
Halaman lain bisa pakai layout masing-masing, tapi kalau mau loader konsisten, salin blok loader ke semua page. [file:590]

## Cara Menjalankan
### 1) Jalankan langsung
Cukup buka `index.html` di browser. [file:590]

### 2) Rekomendasi pakai server lokal (biar aman & konsisten)
Contoh pakai VSCode Live Server atau server statis lain. [file:590]

## Konfigurasi Penting (di `index.html`)
### Toggle View (V1/V2)
State disimpan di:
- `INDEX_VIEW_KEY = "astrionhub_index_view_v1"` [file:590]

### AI Chat (Yuuka)
Histori chat disimpan di:
- `CHAT_KEY = "astrionhub_yuuka_chat_v1"` [file:590]

API yang dipanggil (client-side):
- `NEOXR_ENDPOINT = "https://api.neoxr.eu/api/gpt-pro"` [file:590]
- `NEOXR_APIKEY = "sJSCtQ"` [file:590]
- `USE_PROXY = false` (set `true` kalau kamu punya endpoint backend `/api/yuuka`). [file:590]

> Catatan: Karena request dilakukan dari browser, bisa kena masalah CORS/rate limit tergantung API. Jika kena CORS, pakai mode proxy (`USE_PROXY = true`) dan buat endpoint backend sendiri. [file:590]

## Custom Loader (Page Transition)
Loader muncul saat klik link pindah halaman (same tab), lalu hilang saat page tampil lagi. Mekanisme ini memanfaatkan class `body.is-loading` dan event `pageshow` supaya tidak “nyangkut” saat back/forward. [file:590]

Yang harus ada di setiap halaman agar loader bekerja:
- HTML `#pageLoader` (overlay) [file:590]
- CSS loader (`#pageLoader`, `.loader-card`, dll) [file:590]
- JS loader (event click + `pageshow`) [file:590]

## Ganti Foto Hinako
Cari URL image dan ganti jadi link baru kamu, misalnya:


Biasanya dipakai untuk:
- Foto profile card Hinako (kalau ada section profile).  
- Foto di loader custom (jika loader pakai avatar). [file:590]

## Kustomisasi Cepat
- Ubah nama brand: cari teks `ASTRIONHUB`. [file:590]
- Ubah label navbar: edit anchor di header. [file:590]
- Ubah nomor WhatsApp: cari `https://wa.me/` dan ganti nomor. [file:590]
- Nonaktifkan animasi titik online: hapus class `animate-pulse` di badge online. [file:590]

## Lisensi
Bebas dipakai untuk project pribadi. Kalau untuk publik/komersial, tambahkan lisensi sesuai kebutuhanmu (MIT/Apache-2.0). [file:590]
