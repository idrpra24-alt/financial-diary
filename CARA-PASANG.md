# Catatan Pengeluaran — Cara Pasang di HP

Aplikasi ini adalah web app (PWA). Setelah di-hosting (gratis), bisa Anda pasang
ke home screen HP dan jalan seperti aplikasi biasa, termasuk saat offline.

Isi paket:
- index.html           (aplikasinya)
- manifest.webmanifest (info aplikasi + ikon)
- service-worker.js    (agar bisa offline & terpasang)
- icon-192.png / icon-512.png / apple-touch-icon.png (ikon)

PENTING: semua file harus berada di folder yang sama, dan diakses lewat HTTPS
(bukan dibuka langsung dari file). GitHub Pages sudah HTTPS.

---

## Cara 1 — GitHub Pages (rekomendasi, Anda sudah familiar)

1. Buat repo baru di GitHub, mis. `catatan-pengeluaran` (boleh Private).
2. Upload SEMUA file di folder ini ke root repo (Add file > Upload files).
3. Buka Settings > Pages.
4. Bagian "Build and deployment": Source = "Deploy from a branch",
   Branch = `main`, folder = `/ (root)`. Save.
5. Tunggu ~1 menit, alamatnya muncul:
   `https://NAMA-AKUN.github.io/catatan-pengeluaran/`
6. Buka alamat itu di HP.

## Cara 2 — Netlify Drop (tanpa Git, paling cepat)

1. Buka https://app.netlify.com/drop
2. Seret folder ini ke halaman tersebut.
3. Langsung dapat alamat HTTPS. Buka di HP.

---

## Pasang ke Home Screen

Android (Chrome):
- Buka alamatnya, ketuk menu (titik tiga) > "Tambahkan ke layar utama"
  / "Install app". Ikuti konfirmasi.

iPhone (Safari):
- Buka alamatnya di Safari, ketuk tombol Share (kotak dengan panah) >
  "Add to Home Screen" / "Tambah ke Layar Utama".

Setelah itu ikonnya muncul di home screen dan dibuka layar penuh.

---

## Fitur scan struk (opsional)

Scan struk memakai API Claude milik Anda sendiri:
1. Buka aplikasi, ketuk ikon roda gigi (kanan atas).
2. Tempel API key dari console.anthropic.com.
3. Simpan. Kunci hanya tersimpan di HP Anda.

Model default: claude-haiku-4-5-20251001 (hemat).
Untuk akurasi lebih baik, ganti ke: claude-sonnet-4-6.
Setiap pindai memakai kuota API (biaya kecil). Tanpa API key, pencatatan
manual tetap berfungsi penuh.

## Catatan data
- Data pengeluaran disimpan di penyimpanan browser HP ini (localStorage).
- Data tidak ikut kalau ganti HP/browser. Gunakan "Ekspor CSV" di Pengaturan
  untuk cadangan.
- Membersihkan data situs / uninstall dapat menghapus catatan. Ekspor berkala
  bila datanya penting.
