<p align="center"><img src="https://lh3.googleusercontent.com/xNVBf-W7grp6_AN7qSOq_6ZmUmZDYknF2EwEFfWf46jFbreT1DLmmFudIOTaloliW0s=w300-rw"/><br>
<a href='https://play.google.com/store/apps/details?id=ai.agusibrahim.c2b&pcampaignid=MKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1'><img alt='Temukan di Google Play' src='https://play.google.com/intl/en_us/badges/images/generic/id_badge_web_generic.png'/></a>
</p>
### Pengenalan
**C2Buildozer**  membantu kamu untuk mendistribusikan Game HTML5 dari Construct 2 ke perangkat Android.
Tidak membutuhkan versi berbayar, karena Construct 2 dengan baik hati menyediakan faselitas Export ke HTML5.
C2Buildozer berjalan pada OS Android versi 4.4 (Kitkat) dan diatasnya, jadi untuk pengguna JellyBean (4.1/4.2/4.3) tidak bisa menggunakan C2Buildozer ini.
C2Buildozer bekerja secara offline, sehingga bisa digunakan dalam kondisi apapun.

 **C2Buildozer**  menyediakan pengepakan dengan Cordova saja atau pengepakan Cordova dengan WebView tambahan, yaitu Crosswalk. Bedanya apa? Nanti dijelaskan dibawah

### Bagaimana ini bekerja?
Construct 2 mempermudah pengguna membangun aplikasi/game HTML5 dengan cara WYSWYG, drag drop, tarik pidah, tetapkan event dan action, tapa bersentuhan langsung dengan HTML dan Javascript.
Project hasil Export dari Construct 2 berupa HTML5, jadi pengguna fokus ke HTML5 (HTML/Javascript dan CSS) yg mana ketiganya tidak membutuhkan proses kompilasi untuk dijalankan.
 Jadi sangat membuang waktu jika kita yg berfokus di HTML5 tapi harus melewati proses compiling Android.  **C2Buildozer** memberikan solusi dimana kamu tidak perlu compile program Android (java), C2Buildozer menyediakan prebuild aplikasi yg siap di isi program HTML5. Itu yang membuat proses build di C2Buildozer menjadi lebih cepat.

### Bagaimana cara menggunakannya?
Pertama  **export project**  C2 ke  **TiZEN** , kenapa tizen?
Karena hasil export-an tizen tidak banyak mengandung file-file yang tidak penting di Android, tidak seperti export-an HTML5. Ok, setelah di export,  buka folder hasil export dan  **packing semua ke ZIP**. Selanjutnya kirim ZIP tadi ke Android kamu untuk dibuka melalui  **C2Buildozer** 

* Buka  **C2Buildozer**,  **Select ZIP** lalu arahkan ke ZIP hasil export tadi. klik NEXT.
* Isi detail aplikasi seperti Nama, Package id, versi dan orientasi layar. Jika dirasa sudah cocok, klik NEXT
* Pastikan detail yang tadi dimasukan sudah sesuai, di halaman Review kamu bisa melihatnya. Jika sudah sesuai dan tidak ada yg dirubah, klik NEXT
* Di halaman Signing kamu bisa mensign dengan keystore milikmu sendiri, atau bisa membuat baru. Jika selesai di tahap ini, klik NEXT
* Pilih package untuk aplikasi kamu, default.px adalah Cordova dengan WebView bawaan Android. default.px tidak akan membuat APK kamu membesar, namun ada beberapa keterbatasan. Kamu juga bisa menggunakan Crosswalk dengan cara mendownload PXnya disini http://bit.ly/c2bdepend kemudian meletakan PX tersebut ke /sdcard/C2Buildozer/px. Setelah memilih package, klik NEXT
* Langkah terakhir, klik  **START BUILDING** untuk memulai proses pembuatan APK. Jika selesai klik COMPLETE

Selesai, APK sudah jadi. Tutorial berupa video dapat dilihat disini https://youtu.be/SU5YWgvcC3I

### Menggunakan Live Preview
Live Preview disini masih tahap ujicoba, jadi di beberapa device mungkin tidak bekerja. 
Pertama download dan install dulu C2BLive disini http://bit.ly/c2bdepend pada folder Tools. Kemudian Live Preview bisa dijalankan pada halaman Review.
 **Audio tidak bekerja di Live Preview** 

### Backscreen!!
Untuk mengatasi Blackacreen atau Layar Hitam pada aplikasi/game hasil build, atasi dengan cara  **meng-off-kan WebGL**  pada project properties dan **meng-uncheck  minify script**  pada saat export. Seperti yang dilakukan pada Video berikut https://youtu.be/SU5YWgvcC3I

### Perbedaan Packages
C2Buildozer membawakan package default.px, yaitu template Cordova dengan WebView bawaan Android.
default.px tidak support WebGL/Effect, jika dipaksakan akan mengakibatkan Blackscreen. default.px juga tidak support Audio 😞, namun ada solusi lain untuk menjalankan Audio di default.px, selengkanya tentang audio ada dibawah. Itu yang menyebabkan default.px sangat sederhana dan ukuran APK menjadi lebih kecil
Sementara untuk game yang menggunakan Effect GL dan Audio yang kompleks, disarankan menggunakan package xwalk. Namun xwalk akan menghasilkan APK yg besar, minimal 13MB-an.

### Menjalankan Audio di default.px
Cara menjalankan audio di package default.px yaitu dengan menggunakan [Cordova Native Audio Plugin](https://github.com/floatinghotpot/cordova-plugin-nativeaudio). Untuk menggunakan di C2 gunakan Addon C2Droid, lihat contoh CAPX-nya di http://bit.ly/c2bdepend

### Pasang Admob
Admob disini menggunakan https://github.com/ratson/cordova-plugin-admob-free yang katanya  **berbeda**  dari Plugin Admob yang lainnya. Karena Plugin yang lain berbagi iklan dengan si pembuat Plugin, bahkan diremot dari jauh. Penjelasannya bisa dibaca pada link diatas. Cara memasang Admob ada di contoh CAPX FlyingAlong http://bit.ly/c2bdepend

### Berbagi Kontent/Social Sharing
Berbagi konten seperti skor dapat diterapkan pada game kamu, lihat contoh CAPXnya disini http://bit.ly/c2bdepend, tepatnya di CAPX Flapping Bird

### Membuat Notifikasi Terjadwal
Buat notifikasi terjadwal pada game kamu, misalnya muncul notifikasi "Selamat malam, yuk main lagi" pada malam hari, atau waktu lainnya yang bisa kamu sesuaikan. Contoh CAPX segera menyusul 😅

## Apa saja Plugin Cordova dalam package?
Di Intel XDK mungkin kita pernah memilah-milih plugin, tambah plugin atau menghapusnya. Plugin di C2Buildozer sudah ditetapkan pada Packages, di default.px maupun xwalk memiliki plugin yang sudah ditetapkan. Plugin-plugin Cordova tersebut antara lain:
* https://www.npmjs.com/package/com.peerio.cordova.plugin.social
* https://www.npmjs.com/package/cordova-plugin-admob-free
* https://www.npmjs.com/package/cordova-plugin-device-orientation
* https://www.npmjs.com/package/de.appplant.cordova.plugin.local-notification

Selengkapnya bisa dilihat [disini](https://github.com/agusibrahim/C2BTemplateBuilder/blob/master/www/config.xml)
 
### Membuat Package sendiri
Memmbuat package sendiri memungkinkan kita untuk mengcustom plugin, seperti menambah atau menghapus plugin. Pembuatan dilakukan di [Adobe PhoneGap Build](https://build.phonegap.com) dengan menggunakan repository dari saya https://github.com/agusibrahim/C2BTemplateBuilder.git


### Bagaimana C2Buildozer dibuat?
C2Buildozer dibuat untuk membantu dan mempermudah, itu tujuan awalnya. Aplikasi ini dibuat menggunakan bahasa pemrograman Java. C2Buildozer memang berbeda, dimana tools seperti ini sebenarnya tidak lazim dijalankan dan dibuat untuk Android. Bukan hanya itu membuat C2Buildozer berbeda, parahnya Aplikasi ini dibuat hanya mengguanakan HP Android, ya! Tidak ada bantuan laptop atau PC, apalagi aplikasi Android Studio yang membutuhkan resource besar, 100% dibangun di HP Android dan diketik menggunakan 2 jari pada keyboard sentuh virtual.

### Penutup
Terimakasih telah menggunakan C2Buildozer, semoga App ini bermanfaat. Terimakasih kepada pengurus dan anggota dari grup [Construct 2 & 3 - Tutorial Indonesia](https://facebook.com/groups/690222404368484)
Saran dan Pertanyaan hubungi saya via [Messenger](http://m.me/mynameisagoes)


-------
 Contact pymobile123@gmail.com for help and support or business inquiries

C2Buildozer - Agus Ibrahim
