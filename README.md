# SIG-Teori-Modul14-Calculating-Line-Lengths-and-Statistics-

1. Temukan ne_10m_railroads_north_america.zipfile yang diunduh di panel Browser dan perluas. Seret ne_10m_railroads_north_america.shpfile ke kanvas.

2. Anda akan melihat layer baru ne_10m_railroads_north_americadimuat di panel Layers . Anda akan melihat bahwa layer tersebut memiliki garis yang mewakili rel kereta api untuk seluruh Amerika Utara. Sekarang, mari hitung panjang setiap fitur garis. Pergi ke Memproses ‣ Kotak Alat .

3. Cari dan temukan geometri Vektor ‣ Tambahkan algoritme atribut geometri. Klik dua kali untuk meluncurkannya.

4. Dalam dialog Add Geometry Attributesne_10m_railroads_north_america , pilih sebagai Input layer . Coordinate Reference System (CRS) layer input adalah EPSG:4326 WGS84 . Ini adalah CRS Geografis dengan Lintang dan Bujur sebagai koordinat, WGS84 sebagai ellipsoid dan derajat sebagai satuan. Karena lintang dan bujur tidak memiliki panjang standar, Anda tidak dapat mengukur jarak atau luas secara akurat menggunakan fungsi geometri planar. Untungnya, QGIS menyediakan cara yang lebih baik untuk menghitung jarak menggunakan geometri ellipsoidal, yang merupakan metode paling akurat untuk lapisan yang menjangkau area yang luas seperti ini. Pilih Ellipsoidalsebagai opsi Hitung menggunakan . Klik Jalankan . Setelah proses selesai, klik Tutup.

5. Anda akan melihat layer baru dimuat di panel Layers . Ini adalah salinan dari lapisan input dengan kolom baru yang ditambahkan untuk jarak. Klik kanan layer dan pilih Open Attribute Table .Added geom infoAdded geom info

6. Di Tabel Atribut , Anda akan melihat kolom baru bernama distance . Ini berisi panjang setiap garis fitur dalam meter . Perhatikan juga atribut sov_a3 yang berisi kode negara untuk setiap fitur. Tutup jendela Tabel Atribut .

7. Sekarang setelah kita memiliki panjang segmen jalur kereta api individual, kita dapat menjumlahkannya untuk menemukan panjang total rel kereta api. Tetapi karena pernyataan masalah menuntut kita membutuhkan total panjang rel kereta api di Amerika Serikat, kita harus menggunakan hanya segmen-segmen yang ada di AS. Kita dapat menggunakan nilai kode negara di kolom sov_a3 untuk memfilter layer. Klik kanan layer dan pilih Filter .Added geom info

8. Dalam dialog Pembuat Kueri , masukkan ekspresi berikut dan klik OK .

---------------
"sov_a3" = 'USA'
---------------

9. Anda akan melihat ikon Filter muncul di sebelah layer di panel Layers yang menunjukkan bahwa filter diterapkan ke layer. Anda juga dapat mengonfirmasi secara visual bahwa lapisan tersebut sekarang berisi segmen garis hanya untuk Amerika Serikat. Sekarang kita siap menghitung jumlahnya. Klik tombol Tampilkan ringkasan statistik pada Bilah Alat Atribut .Added geom info

10. Panel Statistik baru akan terbuka. Pilih lapisan dan kolom.Added geom infolength

11. Anda akan melihat berbagai statistik ditampilkan di panel. Satuan statistik sama dengan satuan lengthkolom- meter . Mari ubah perhitungan untuk menggunakan kilometer sebagai gantinya. Klik ikon Ekspresi di sebelah menu tarik-turun bidang di panel Statistik .

12. Masukkan ekspresi berikut dalam Dialog Ekspresi yang mengubah panjang menjadi kilometer.

-------------
length / 1000
-------------

13. Nilai Jumlah yang ditampilkan adalah total panjang rel kereta api di AS.
