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
Specifies a condition that must evaluate to true in order to execute a command.

Syntax
IF test command
Parameters
Name	Description
test	
The condition that must be met for command to be run.

command	
Any valid ACLScript command to run if test evaluates to true.

Examples
Running a command conditionally
You want to use CLASSIFY on a table, but only if the v_counter variable is greater than ten:

IF v_counter > 10 CLASSIFY ON Location TO "Count_by_Location.fil" OPEN
Running a command based on a user decision
You want to allow the script user to decide whether to classify a table.

In your script, you include a dialog box with a check box that if selected allows the CLASSIFY command to run. The check box stores a True or False input value in the logical variable v_classify_checkbox.

You use an IF test to determine the value of v_classify_checkbox, and if the value is True, CLASSIFY executes:

IF v_classify_checkbox=T CLASSIFY ON Location TO "Count_by_Location.fil" OPEN
Remarks
IF command versus IF parameter
The logic of the IF command differs from the IF parameter that is supported by most commands:

IF command determines whether the associated command runs or not, based on the value of the test expression
IF parameter determines whether the command runs against each record in an Analytics table based on the value of the test expression
Decision making in scripts
In a script, you can enter a series of IF command tests and run different commands based on the results. The IF command can be also be used to test the value of a variable to determine if further processing should occur.


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
Calculates the total value of one or more fields in an Analytics table.

Syntax
TOTAL {<FIELDS> numeric_field <...n>|<FIELDS> ALL <EXCLUDE numeric_field <...n>>} <IF test> <WHILE test> <FIRST range|NEXT range>
  
  Totaling the first 25 records
You calculate the total amount of the MKTVAL field for the first 25 records in the table:

TOTAL FIELDS MKTVAL FIRST 25
Remarks
When to use TOTAL
Use TOTAL to verify the completeness and accuracy of the source data and to produce control totals. The command calculates the arithmetic sum of the specified fields or expressions.
  
## Fungsi Search
Melalui perintah STATISTICS Auditor dapat memperoleh informasi yang lebih lengkap dari perintah PROFILE, termasuk untuk jenis data Tanggal/Date.
Perintah STATISTIC dilakukan melalui Menu : Analyze > Statisitical > Statistics
Tentukan Field apa yang akan distatistik, dan tentukan kriteria, jika ada.
Tentukan parameter # of High/Low pada tab More

## Fungsi Statistik
Melalui perintah STATISTICS Auditor dapat memperoleh informasi yang lebih lengkap dari perintah PROFILE, termasuk untuk jenis data Tanggal/Date.
  Statistics
Statistics provide an overview of the data in a table that you can use to identify trends or irregularities.
● Perintah STATISTIC dilakukan melalui Menu : Analyze > Statisitical > Statistics
● Tentukan Field apa yang akan distatistik, dan tentukan kriteria, jika ada.
● Tentukan parameter # of High/Low pada tab More
