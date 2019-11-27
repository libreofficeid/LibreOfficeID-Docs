# Menyiapkan Berkas Konfigurasi

Setelah Anda menyiapkan aset-aset gambar, sekarang mari menyiapkan berkas-berkas konfigurasi. Berikut adalah beberapa berkas konfigurasi yang harus Anda siapkan:

1. **persona\_list.txt**   


   **persona\_list.txt** merupakan berkas konfigurasi untuk mengatur bagaimana tema kita akan ditampilkan. Berkas terserbut memuat informasi sebagai berikut:

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

2. **sofficerc  
   sofficerc** merupakan berkas yang akan mengatur bagaimana splash akan ditampilkan. Berikut merupakan isi dari berkas sofficerc dan beberapa penjelasannya.

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

   Untuk melakukan kustomsisasi tampilan Anda hanya perlu menyunting beberapa parameter berikut;  
  
   **A. Logo**  
   Parameter untuk menentukan apakah splash ditampilkan atau tidak  
  
   **B. NativeProgress**  
   Menampilkan _progressbar_ native atau kustom  
  
   **C. ProgressBarColor**  
   ProgressFrameColor menentukan warna bingkai pada _progressbar_, parameter ini menggunakan nilai warna RGB  
  
   **D. ProgressPosition**  
   Menentukan lokasi _progressbar_, parameter ini menggunakan nilai koordinat X dan Y   
  
   **E. ProgressSize**  
   Menentukan ukutan dari _progressbar_, parameter ini menggunakan nilai lebar dan tinggi dengan satuan piksel.

