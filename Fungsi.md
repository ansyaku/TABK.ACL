## Fungsi Verify
Sebelum melakukan analisis, auditor perlu melakukan pengecekan terhadap kelengkapan data, salah satu caranya adalah dengan menggunakan **Verify**.<br>
*Step:*<br>
Menu Bar : Data > Verify <br>
Kapan fungsi verify menghasilkan nilai TRUE ?
* __character fields__ hanya mengandung karakter yang dapat diprint seperti huruf, bilangan, dan simbol.
* __numeric fields__ hanya mengandung karakter numerik, seperti angka, desimal, dan simbol mata uang.
* __datetime fields__ hanya mengandung tanggal (date), tanggal dan waktu, atau waktu yang valid .

**NOTES:**<br>
Untuk *computed fields* dan *expressions* :<br>
*Computed fields* dan *expressions* apabila di-*verify* apabila dievaluasi selalu menghasilkan *T (true)*, jadi apabila ada computed fields dan expressions harus dikonversi menjadi kolom fisik.


## Fungsi Search
Auditor juga dapat melakukan verifikasi manual atas data dengan melakukan pencarian data sesuai kriteria verifikasi yang diinginkan.
Auditor dapat melakukan perintah SEARCH melalui Menu Bar : Data > Search
Kemudian nomor record yang akan dicari, atau Menentukan menentukan kriteria verifikasi

## Fungsi IF
Pada seluruh perintah yang ada di dalam ACL auditor dapat menetapkan suatu kriteria yang akan membatasi pengujian yang dilakukan.
Penetapan kriteria ini disebut dengan EXPRESSION.
Pada perintah COUNT, TOTAL, PROFILE, dan STATISTICS, pilih IF

## Fungsi Count
Pada seluruh perintah yang ada di dalam ACL auditor dapat menetapkan suatu kriteria yang akan membatasi pengujian yang dilakukan.
Penetapan kriteria ini disebut dengan EXPRESSION.
Pada perintah COUNT, TOTAL, PROFILE, dan STATISTICS, pilih IF
Fungsi Counts berguna untuk menghitung jumlah baris pada tampilan yang sedang tampil (bisa juga dikombinasikan dengan kondisi (IF) untuk menspesifikasi).
Syntax : <br>
COUNT <IF test> <WHILE test> <FIRST range|NEXT range>
  
*Bagaimana filter mempengaruhi COUNT ?* <br>
Apabila filter telah dilakukan sebelumnya, maka perintah counts hanya menghitung baris yang ada setelah filter diaplikasikan.
  
## Fungsi Total
Pada seluruh perintah yang ada di dalam ACL auditor dapat menetapkan suatu kriteria yang akan membatasi pengujian yang dilakukan.
Penetapan kriteria ini disebut dengan EXPRESSION.
Pada perintah COUNT, TOTAL, PROFILE, dan STATISTICS, pilih IF

## Fungsi Search
Melalui perintah STATISTICS Auditor dapat memperoleh informasi yang lebih lengkap dari perintah PROFILE, termasuk untuk jenis data Tanggal/Date.
Perintah STATISTIC dilakukan melalui Menu : Analyze > Statisitical > Statistics
Tentukan Field apa yang akan distatistik, dan tentukan kriteria, jika ada.
Tentukan parameter # of High/Low pada tab More

## Fungsi Statistik
Melalui perintah STATISTICS Auditor dapat memperoleh informasi yang lebih lengkap dari perintah PROFILE, termasuk untuk jenis data Tanggal/Date.
● Perintah STATISTIC dilakukan melalui Menu : Analyze > Statisitical > Statistics
● Tentukan Field apa yang akan distatistik, dan tentukan kriteria, jika ada.
● Tentukan parameter # of High/Low pada tab More
