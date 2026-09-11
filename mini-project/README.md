# Mini Project - Portal Kegiatan D3 Teknik Informatika

## Ringkasan produk

Landing page statis untuk **Portal Kegiatan D3 Teknik Informatika**, sebagai
kelanjutan tema dari Independent Challenge (artikel lokakarya web dan
pricing card). Target pengguna adalah mahasiswa D3 Teknik Informatika yang
ingin mengikuti kegiatan kampus seperti lokakarya dan workshop dasar web.

- **Headline**: "Ikuti Kegiatan Kampus, Asah Kemampuan Coding-mu"
- **Supporting statement**: Portal ini menghimpun lokakarya, workshop, dan
  pelatihan singkat untuk membantu mahasiswa belajar web dari dasar.
- **Primary CTA**: "Lihat Jadwal Kegiatan" yang mengarah ke bagian
  #daftar.

## Struktur konten

1. header - brand dan navigasi (Manfaat, Kegiatan, Daftar).
2. section#beranda (hero) - headline, supporting statement, CTA utama,
   dan gambar dokumentasi kegiatan.
3. section#manfaat - tiga feature-card (Belajar dari Dasar, Code
   Defense, Sertifikat Kegiatan) memakai Flexbox dan dapat wrap.
4. section#kegiatan - daftar kegiatan mendatang memakai elemen time
   dengan atribut datetime yang valid.
5. section#daftar (CTA) - ajakan bergabung dengan tombol email.
6. footer - identitas program studi.

## Keputusan teknis

- Struktur semantik dipilih agar setiap bagian punya satu h2/h3 dan
  bermakna sesuai isinya (bukan sekadar div).
- Layout memakai Flexbox saja (nav, .hero-content, .feature-list)
  dengan satu breakpoint di 768px, konsisten dengan pendekatan mobile-first
  pada Task 3 praktikum.
- Aksesibilitas dasar: lang="id", alt deskriptif pada gambar, kontras
  teks putih di atas warna primer, serta :focus-visible pada semua
  tautan dan tombol.

