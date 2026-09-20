# yora1928.my.id

Situs pribadi YORA (yora1928). HTML dan CSS murni. Tanpa JavaScript, tanpa build, tanpa pelacak.

## Isi folder
```
index.html      Halaman utama (semua konten ada di sini, gampang diedit)
404.html        Halaman "tidak ditemukan"
css/style.css   Tampilan (warna ada di bagian :root paling atas)
assets/         favicon.svg dan og-image.png (1200x630, untuk pratinjau saat tautan dibagikan)
CNAME           Berisi yora1928.my.id (dibaca GitHub Pages)
robots.txt      Izin untuk mesin pencari + alamat sitemap
sitemap.xml     Peta situs
.nojekyll       Supaya GitHub Pages tidak memakai Jekyll
```

## 1. Tayang di GitHub Pages dengan domain sendiri
Urutan ini penting. Tambahkan domain ke GitHub DULU, baru atur DNS. Kalau dibalik, orang lain berpotensi memakai domainmu.

1. Buat repositori publik `yora1928.github.io` di akun yora1928, lalu upload semua isi folder ini ke root.
2. Buka Settings > Pages. Source: Deploy from a branch, branch `main`, folder `/ (root)`. Simpan.
3. Di kolom "Custom domain" isi `yora1928.my.id` (tanpa www), simpan.
4. Di panel DNS tempat kamu membeli domain, buat record berikut (hapus record bawaan yang bentrok):

| Tipe  | Host | Nilai              |
|-------|------|--------------------|
| A     | @    | 185.199.108.153    |
| A     | @    | 185.199.109.153    |
| A     | @    | 185.199.110.153    |
| A     | @    | 185.199.111.153    |
| CNAME | www  | yora1928.github.io |

   Opsional untuk IPv6, buat record AAAA di @ ke 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, dan 2606:50c0:8003::153. Cek nilai terbaru di dokumentasi GitHub "Managing a custom domain for your GitHub Pages site".
5. Tunggu DNS aktif (bisa sampai 24 jam), lalu di Settings > Pages centang **Enforce HTTPS**.
6. Buka `https://yora1928.my.id` dan `https://www.yora1928.my.id` untuk memastikan keduanya jalan.

## 2. Daftarkan ke Google (supaya situs bisa dicari)
1. Buka Google Search Console, tambah properti bertipe **Domain** dengan `yora1928.my.id`. Verifikasi lewat record TXT di panel DNS yang sama.
2. Buka menu Sitemaps, kirim `https://yora1928.my.id/sitemap.xml`.
3. Buka URL Inspection, tempel `https://yora1928.my.id/`, klik **Request indexing**.
4. Beberapa hari kemudian, cek dengan mengetik `site:yora1928.my.id` di Google.
5. Ulangi di Bing Webmaster Tools (bisa impor langsung dari Search Console).

Indeks pertama biasanya butuh beberapa hari sampai beberapa minggu. Tidak ada yang bisa menjamin peringkat tertentu.

## 3. Pasang tautan balik dari GitHub (paling berpengaruh)
Halaman GitHub yora1928 sudah dikenal Google. Tautan dari sana membantu Google menemukan dan mempercayai situsmu:
- Profil GitHub: isi kolom **Website** dengan `https://yora1928.my.id`.
- README profil (`yora1928/yora1928`): tambahkan tautan ke situs.
- Tiap repositori: bagian About > isi **Website** dengan `https://yora1928.my.id`.
- Pakai nama yang sama (YORA / yora1928) di semua tempat supaya Google mengenalinya sebagai satu identitas.

## 4. Yang membuat situs benar-benar naik
Pengaturan teknis hanya membuat situs bisa ditemukan. Yang membuatnya dipercaya adalah isi yang nyata dan terus bertambah:
- Tambahkan catatan lab yang ditulis dengan kata-katamu sendiri, misalnya cara kamu membangun lab jaringan atau apa yang kamu pelajari dari satu topik. Satu tulisan jujur lebih berguna daripada banyak kata kunci.
- Perbarui halaman tiap ada sertifikat, proyek, atau tulisan baru, lalu ubah tanggal `lastmod` di `sitemap.xml` dan `dateModified` di `index.html`.

## Mengedit isi
- Semua teks ada di `index.html`. Cari dengan Ctrl+F lalu ganti.
- Mau menampilkan email: buka bagian `#kontak`, ikuti contoh di komentar HTML.
- Mau menampilkan nama lengkap: tambahkan di bagian `#tentang` dan di `alternateName` pada data JSON-LD di `<head>`. Ini membantu orang yang mencari nama aslimu, tapi mengurangi privasi, jadi pertimbangkan dulu.
- Kalau domain berubah, ganti `https://yora1928.my.id` di `index.html`, `robots.txt`, `sitemap.xml`, dan isi file `CNAME`.
