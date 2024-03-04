# AutopsyExercise---1203210098
"Langkah-langkah Percobaan Digital Forensic Investigation dengan menggunakan Autopsy."

1. Download Autopsy dan HxD sebagai aplikasi yang akan digunakan, dengan memisahkan lokasi penyimpanan ke D Drive agar data tidak tercampur dengan file lain dan memudahkan pencarian.
2. Di dalam D Drive file dipisahkan kembali dengan membentuk folder bernama hashset dan CASES yang digunakan sebagai penyimpanan case-case investigasi yang akan dilakukan nantinya. CASES dikelompokkan kembali dalam folder dengan nama yang memuat:
   1. Nomor case
   2. Tipe investigasi (berupa 1 huruf representasi case yang akan diinvestigasi)
   3. Tag lokasi
   4. Member name (inisial)
3. Di dalam folder case yang telah dibuat, akan diisi piranti-piranti penting yang menjadi kebutuhan dalam melakukan investigasi dengan contoh sebagai berikut.
   1. Docs, sebagai tempat penyimpanan dokumen atau catatan yang memuat timestamp, detail jalannya investigasi, dan hal yang berhubungan dalam pelaksanaan investigasi.
   2. Images, untuk menyimpan gambar-gambar terkait dan sebagai dokumentasi.
   3. Autopsy, sebagai base directory.
   4. Reports, berisi kumpulan laporan hasil investigasi.
4. Selanjutnya adalah dengan membuka aplikasi Autopsy yang telah diinstall sebelumnya, lalu create New Case sebagai percobaan, dengan mengisi nama case sesuai dengan nama folder dalam CASES yang telah dibuat sebelumnya. Dan tidak lupa untuk menyimpannya dalam D Drive.
5. Dilanjutkan dengan mengisi beberapa informasi opsional, lalu melakukan pengaturan Data Source sebagai berikut.
   1. Specify host name berisi nama docs cases, dicontohkan dengan "Exhibit001".
   2. Data Source Type dicontohkan dengan memilih Disk Image, karena file image yang akan digunakan berformat DD file yang merupakan file mentah.
   3. Select Data Source berisi path dari lokasi penyimpanan file image.
   4. Ingest modules dengan banyak section yang berisi pengaturan mengenai bagaimana data akan diproses. Dengan penjelasan sebagai berikut.
       1. Recent Activity: memuat aktivitas terkini dalam sistem yang kemudian akan diekstrak dalam beberapa kategori sehingga memudahkan kegiatan investigasi.
       2. Hash Lookup: mengkategorikan 'bad' dan 'good' hash value yang dapat dimuat jika didalamnya terdapat sesuatu yang mencurigakan.
       3. File Type Identification: dapat meng-set tipe file yang ingin dihubungkan berdasarkan angka binary file tersebut.
       4. Extension Mismatch Detector: mendeteksi kesalahan extension pada file yang sudah dihubungkan.
       5. Embedded File Extractor: berisi file hasil kompresi.
       6. Picture Analyzer: memuat informasi yang ada dalam file gambar.
       7. Keyword Search: dapat digunakan untuk membuat keyword list pribadi.
       8. Email Parser: membuat email dapat tetap tersedia dan dapat digunakan.
       9. Encryption Detection: digunakan untuk menemukan file yang telah dienkripsi menggunakan tes Entropy. Namun, dibutuhkan waktu yang cukup lama.
       10. Interesting Files Identifier: mengumpulkan file yang terhubung dengan kriteria yang diinginkan pengguna.
       11. Central Repository: menemukan case yang mungkin berhubungan dengan case selanjutnya, sehingga dapat membantu membuat pattern yang lebih spesifik.
       12. PhotoRec Carver: membantu menemukan data yang telah hilang atau dihapus sebelumnya.
       13. VM Extractor: mengekstrak virtual machine yang ada pada tipe file gambar.
       14. Data Source Integrity: memberi informasi mengenai nilai hash suatu data.
       15. Android Analyzer: menganalisa device android.
       16. DJI Drone Analyzer: menganalisa drone.
       17. Paso: forensik tools untuk mengekstrak banyak data.
       18. YARA Analyzer: untuk menganalisa struktur file dan mendeteksi malware pada sistem.
       19. IOS Analyzer: menganalisa device IOS.
       20. GPX Parser: sebagai pendeteksi lokasi.
   5. Dilanjutkan dengan loading proses penambahan Data Source ke database lokal.
6. Data Source telah berhasil dibuat.
7. Dalam Data Source pengguna dapat mengetahui struktur file, nama file, timestamp yang menunjukkan kapan file dimodifikasi, diubah, dan diakses, size file, flags, hash, MIME type, extension, dan lokasi dimana file disimpan. Dan jika file diklik akan menampilkan main view dari file tersebut.
8. Pada bagian bawah Data Source terdapat File Views yang dapat dengan otomatis memfilter tampilan mana yang ingin dilihat atau yang sedang dicari. Sebagai contoh klik 'By Extension', maka akan menampilkan images yang diurutkan berdasarkan extensinya.
9. Pengguna juga dapat merecovery data yang telah dihapus sebelumnya dengan mengklik bagian 'Deleted Files'.
10. Data Artifacts, berisi semua informasi dari data-data yang telah diatur formatnya pada Ingest Modules sebelumnya.
11. Pada bagian Analysis Results, akan memuat hasil dari pencarian Keyword Lists dan Keyword Search. Keyword Lists akan digunakan untuk mencari kata umum yang mungkin relevan dengan tipe case yang telah dimasukkan. Sedangkan pada Keyword Search akan digunakan untuk mencari kata yang lebih spesifik dalam case-case individual. Hasil pencarian dapat diberi tag atau bookmark dan dapat dikelompokkan kembali, sehingga pengguna dapat membentuk report yang memuat banyak informasi penting yang saling berkaitan. Hasil tag akan dimuat dalam menu 'Tags'.
12. Selanjutnya, hasil report dapat digenerate menjadi link HTML, dokumen excel, file text, dan masih banyak lagi. Sebagai contoh pengguna mengubah data report menjadi data dalam link HTML. Pada bagian tengah atas pengguna dapat mengklik 'Generate Report', lalu memilih tipe HTML Report dengan data source yang telah diatur sebelumnya. Pengguna juga dapat memilih data mana yang akan direport. Selanjutnya, Autopsy akan memberi link hasil dari report data yang telah dilakukan. Pengguna dapat membagikan link pada siapa saja dengan kondisi data didalamnya dapat dilihat oleh siapapun yang memiliki link. File hasil report dapat diakses dalam file 'Reports'.
