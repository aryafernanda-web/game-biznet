# Speed Button Game — Biznet

Game timer sederhana (single-page, statis: HTML/CSS/JS saja, tanpa backend).

## Cara Deploy ke Vercel

### Opsi A — Lewat Dashboard Vercel (paling mudah)
1. Buka https://vercel.com dan login/daftar.
2. Klik **Add New → Project**.
3. Upload folder ini (atau hubungkan ke repo GitHub yang berisi folder ini).
4. Framework Preset pilih **Other** (Vercel akan otomatis mendeteksi ini sebagai situs statis).
5. Klik **Deploy**. Selesai — Anda akan mendapat URL seperti `https://nama-project.vercel.app`.

### Opsi B — Lewat Vercel CLI
```bash
npm install -g vercel
cd speedbutton-vercel
vercel login
vercel        # deploy preview
vercel --prod # deploy ke production
```

### Opsi C — Lewat GitHub
1. Push folder ini ke repository GitHub baru.
2. Di dashboard Vercel: **Add New → Project → Import Git Repository**.
3. Pilih repo tersebut, biarkan pengaturan default (statis, tanpa build command khusus), lalu **Deploy**.

## Struktur File
- `index.html` — seluruh aplikasi (HTML, CSS, JS dalam satu file).
- `vercel.json` — konfigurasi routing untuk Vercel. Sengaja mematikan langkah build (`buildCommand`/`installCommand`: false) karena ini situs statis murni, tidak ada proses build sama sekali.

## Catatan
- Semua data (skor, waktu terbaik, riwayat, nama hadiah) disimpan di `localStorage` browser pengguna — data tidak tersimpan di server, jadi tiap pengguna/browser punya datanya sendiri-sendiri.
- Riwayat sekarang bisa dihapus dengan dua cara:
  - **Hapus satu per satu**: klik tombol "✕ Hapus" pada tiap item riwayat.
  - **Hapus semua sekaligus**: klik ikon 🗑 di pojok kanan atas kartu "Riwayat Terakhir".
