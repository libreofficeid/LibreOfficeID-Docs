# Membuat Tema Sendiri

Berikut langkah-langkah yang dapat Anda ikuti untuk membuat tema kustom LibreOffice.

#### Hirarki Folder Tema

LO-TC menyusun konfigurasi tema dalam sebuah hirarki folder khusus agar mempermudah siapa saja yang ingin membuat kustom tema dan memasangnya menggunakan LO-TC. Simpan dan tempatkan masing-masing aset yang nantinya akan dibuat ke dalam direktori **themes**. LO-TC akan secara otomatis membaca daftar tema yang terdapat pada direktori, kami menyebutnya tema siap pasang.

silakan perhatikan hirarki direktori berikut ini untuk membantu Anda mengetahui di mana lokasi penyimpanan aset-aset yang akan Anda buat pada langkah-langkah selanjutnya.

```bash
themes
└── nama-tema
    ├── program
    │   ├── intro.png
    │   └── sofficerc
    ├── screenshot.png
    └── share
        └── gallery
            └── personas
                ├── nama-tema
                │   ├── footer.png
                │   ├── header.png
                │   └── preview.png
                └── personas_list.txt
```

\[UPDATE\] Kami telah menyediakan perkakas tambahan untuk membantu Anda membuat folder tema secara lengkap dan cepat. Cukup jalankan perintah:

```bash
$ bash theme-creator.sh
```

kemudian masukkan nama tema yang Anda inginkan. Secara otomatis LO-TC akan membuat direktori tema sesuai dengan nama yang Anda masukkan ke dalam folder `themes`

#### Menyiapkan Aset-Aset Gambar

Gambar-gambar yang harus dipersiapkan untuk membuat tema ini antara lain:

1. Splash Splash merupakan gambar yang pertama kali muncul ketika Anda menjalankan LibreOffice. Sebenarnya tak ada ukurab baku untuk gambar splash ini, namun kami sarankan untuk menggunakan ukuran yang juga digunakan oleh LibreOffice yaitu 661 x 169 piksel. Anda dapat membuat splash menggunakan template yang sudah kami sediakan. Silakan unduh melalui [tautan ini](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/intro.svg)
2. Header Header merupakan gambar yang tampak pada bagian atas program LibreOffice, tepatnya di area menu LibreOffice. Standar ukuran header ini kami ambil dari standar ukuran aset gambar pada tema-tema persona. Kami sangat menyarankan agar desain yang dibuat untuk header ini memanfaatkan area pojok kanan atas. Alasan teknisnya adalah karena area ini merupakan area palinga aman dan tidak mengganggu visibilitas ikon-ikon pada menu. Kami telah menyiapkan template header yang siap untuk dimodifikasi. Silakan unduh melalui [tautan ini](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/header.svg)
3. Footer Footer merupakan gambar yang akan tampil pada area bawah program LibreOffice. Pada dasarnya footer ini akan tersembunyi secara otomatis apabila tidak ada menu yang terbuka pada bagian bawah/footer LibreOffice. Area aman untuk footer ini berada di sisi kanan, silakan gunakan template yang telah kami sediakan untuk memabantu Anda membuat footer. Template dapat [diunduh di sini](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/footer.svg)
4. Preview Preview merupakan gambar yang akan ditampilkan pada menu `perkakas` --&gt; `Opsi`--&gt; `Personalisasi`. Preview ini menjadi identitas tema Anda. Area aman untuk gambar preview ini berada di bagian tengah are. Silakan untuh template preview yang telah kami sediakan [melalui tautan ini](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/preview.svg)
5. Screenshot \(opsinal\) Bantu para pengguna lain untuk memngenali tema Anda dengan memberikan screenshot ketika tema Anda berhasil terpasang.

#### Membuat Konfigurasi

Setelah Anda menyiapkan aset-aset gambar, sekarang mari menyiapkan berkas-berkas konfogurasi. Berikut adalah beberapa berkas konfigurasi yang akan kita kita siap:

1. sofficerc `sofficerc` merupakan berkas yang akan mengatur bagaimana splash akan ditampilkan. Berikut merupakan isi dari berkas sofficerc dan beberapa penjelasannya.

   ```bash
   [Bootstrap]
   CrashDirectory=${$BRAND_BASE_DIR/program/bootstraprc:UserInstallation}/crash
   HideEula=1
   Logo=1
   NativeProgress=false
   ProgressBarColor=0,0,0
   ProgressFrameColor=102,102,102
   ProgressPosition=35,153
   ProgressSize=444,8
   ProgressTextBaseline=145
   ProgressTextColor=0,0,0
   SecureUserConfig=true
   SecureUserConfigCompress=true
   SecureUserConfigExtensions=true
   SecureUserConfigMode=1
   SecureUserConfigNumCopies=2
   URE_BOOTSTRAP=${ORIGIN}/fundamentalrc
   ```

   untuk melakukan kustomsisasi tampilan Anda hanya perlu menyunting parameter, `logo`, `NativeProgress`, `ProgressBarColor`, `ProgressFrameColor`, `ProgressPosition`, dan `ProgressSize`

   * Logo -- parameter untuk menentukan apakah splash ditampilkan atau tidak
   * NativeProgress -- Menampilkan _progressbar_ native atau kustom
   * ProgressBarColor -- Menentukan warna _progressbar_, parameter ini menggunakan nilai warna RGB
   * ProgressFrameColor --  Menentukan warna bingkai pada _progressbar_, parameter ini menggunakan nilai warna RGB
   * ProgressPosition -- Menentukan lokasi _progressbar_, parameter ini menggunakan nilai koordinat X dan Y 
   * ProgressSize -- Menentukan ukutan dari _progressbar_, parameter ini menggunakan nilai lebar dan tinggi dengan satuan piksel

2. persona\_list.txt `persona_list.txt` merupakan berkas konfigurasi untuk mengatur bagaimana tema kita akan ditampilkan. Berkas terserbut memuat informasi sebagai berikut:

   * Nama Direktori Tema
   * Nama Tema \(akan muncul sebagai tooltip\)
   * Lokasi berkas preview
   * Lokasi berkas header
   * Lokasi berkas footer
   * Warna backgrond dan foreground

   Berikut merupakan contoh format penulisan informasi di atas \(misalnya tema yang dibuat bernama _**rainbow**_\).

   ```bash
   rainbow;Rainbow;rainbow/preview.png;rainbow/header.png;rainbow/footer.png;;#ffffff;#000000
   ```

Setelah semua aset dan berkas konfigurasi siap, silakan jalankan LO-TC, jika langkah-langkah yang dilakukan benar, seharusnya tema Anda akan muncul sebagai daftar tema yang siap pakai.



