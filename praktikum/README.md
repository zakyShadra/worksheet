# Praktikum Modul 1 - Zaky Shadra Ibnu Hibban / 251511031

## Ringkasan halaman

Halaman index.html adalah profil mahasiswa sederhana hasil perbaikan dari kode awal yang seluruhnya memakai div. Struktur akhir terdiri dari
header (judul halaman dan nav), main yang membungkus tiga section kartu (Tentang, Keterampilan, Kontak), dan footer. Tampilan dibangun
dengan satu file css/style.css memakai custom property, class reusable (.container, .card, .nav-link, .button), dan layout Flexbox yang
menyesuaikan diri mulai dari 320px sampai desktop.

## Tiga keputusan teknis

1. **Mengganti seluruh div pembungkus konten menjadi elemen semantik**
   (header, nav, main, section, footer) supaya struktur dokumen menjelaskan makna tiap bagian, bukan cuma tampilan. Tiga kartu tetap
   memakai section (bukan article) karena isinya adalah bagian dari satu halaman profil, bukan konten yang berdiri sendiri.
2. **Menyusun kartu dengan Flexbox lewat class .card-list dan .card**
   alih-alih tabel atau position: absolute, supaya urutan baca tetap logis dan kartu bisa berpindah dari satu kolom (mobile) menjadi satu
   baris (desktop) hanya dengan mengubah flex-direction di media query.
3. **Memilih breakpoint 768px** karena pada lebar itu ketiga kartu masih cukup lebar untuk dibaca berdampingan tanpa teks jadi terlalu sempit
   di bawah itu, satu kolom lebih nyaman dibaca di layar kecil.

## Masalah, diagnosis, dan perbaikan

| No  | Gejala                                                                                                   | Penyebab                                                               | Perbaikan                                                                                                    |
| --- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| 1   | Pada lebar 320px, tautan navigasi berpotensi keluar dari layar karena berjejer dalam satu baris kaku     | nav belum diberi flex-wrap, sehingga tiga tautan dipaksa satu baris    | Menambahkan display:flex; flex-wrap:wrap; gap:1rem; pada nav agar tautan bisa turun baris                    |
| 2   | Tautan email di bagian Kontak tidak terlihat seperti tombol aksi dan sulit dibedakan saat fokus keyboard | Tautan masih berupa teks polos tanpa penanda visual maupun state fokus | Mengubah tautan menjadi class .button dengan background, padding, serta :hover dan :focus-visible yang jelas |

## Hasil pengujian empat viewport

Diuji melalui Device Toolbar pada lebar 320px, 375px, 768px, dan 1024px:

- **320px & 375px**: kartu tersusun satu kolom, navigasi turun baris rapi,
  gambar profil menyesuaikan lebar kontainer (max-width:100%), tidak ada
  horizontal scroll.
- **768px & 1024px**: navigasi sejajar dengan judul, tiga kartu tersusun
  satu baris dengan lebar yang sama besar (flex:1), tidak ada overflow.

## Refleksi belajar

Bagian paling menantang dari praktikum ini adalah memahami bahwa perbaikan semantik pada Task 1 harus dilakukan tanpa mengubah konten yang tampil,
hanya membungkusnya ulang dengan elemen yang tepat. Awalnya saya sempat ingin langsung menambahkan class dan CSS di Task 1, tapi modul menegaskan
struktur harus benar dulu sebelum tampilan diatur. Hal lain yang baru benar-benar saya pahami adalah bagaimana box-sizing: border-box membuat
padding dan border tidak menambah lebar akhir elemen, sehingga kartu dengan padding: 1.5rem tetap pas di dalam .card-list tanpa perlu
menghitung manual. Menentukan breakpoint juga mengajarkan saya untuk melihat konten dulu (kapan tiga kartu mulai terasa sempit) daripada
menebak ukuran perangkat tertentu. Kesalahan kecil soal navigasi yang berpotensi overflow di 320px cukup berharga karena mengingatkan saya untuk
selalu menambahkan flex-wrap setiap kali membuat flex container yang isinya bisa bertambah. Ke depannya saya ingin lebih terbiasa membaca tab
Computed di DevTools tanpa harus menebak-nebak nilai akhir sebuah elemen, serta lebih disiplin menjalankan validator W3C sebelum menganggap sebuah
halaman selesai.

## Log AI atau sumber bantuan

Struktur HTML semantik, penulisan CSS (custom property, Flexbox, media query), dan dokumen README ini disusun manual namun di bantu pemahaman dan
penulisan code nya dibantu oleh AI.
