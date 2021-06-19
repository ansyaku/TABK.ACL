# Perolehan Data

Untuk mengimpor data, ACL dapat menarik data yang berasal dari beragam database/file, antara lain :
1. Active Directory - 64 bit
2. Google BigQuery - 64 bit
3. JSON - 64 bit
4. LDAP - 64 bit
5. MongoDB - 64 bit
6. MySQL - 64 bit
7. Oracle - 64 bit
8. Spark - 64 bit
9. SQL Server - 64 bit
10. Microsoft Access - 64 bit
11. ACL Connector for CSV - 64 bit
12. PostgreSQL ANSI(x64) - 64 bit
13. PostgreSQL Unicode(x64) - 64 bit
14. ODBC Driver 17 for SQL server (2019)- provides native connectivity from Windows, Linux, & macOS to SQL Server and Azure SQL Databases
15. SQL Server Native Client (2012)- can be used for both SQL OLE DB provider and SQL ODBC driver for Windows
16. SQL Server (2000 - lama) does not support some of the new features in SQL Server 2005 and above. 

## Koneksi ke File Excel
Untuk koneksi ke file XLS, atua XLSX, bisa dilakukan dengan tahap-tahap berikut :
* Toolbar **Import** >> **File**<br><br>
  ![SQL1](https://github.com/ansyaku/tabk.acl/blob/main/img/SQL1.png)
  <br><br>
* Pilih Excel
  <br><br>
  ![Excel1](https://github.com/ansyaku/tabk.acl/blob/main/img/Excel1.png)
  <br><br>

* Pilih
  <br><br>
  ![Excel2](https://github.com/ansyaku/tabk.acl/blob/main/img/Excel2.png)
  <br><br>

* Selanjutnya akan muncul resume terkait dengan pilihan yang telah kita buat. Apabila dirasa sudah cocok, maka dapat dilanjutkan dengan mengklik **Finish**.
## Koneksi ke File CSV atau TXT
Untuk koneksi ke file CSV atau TXT, bisa dilakukan dengan tahap-tahap berikut :
Untuk koneksi dari ACL ke SQL Server, dapat dilakukan tahap-tahap berikut :
* Toolbar **Import** >> **File**<br><br>
  ![SQL1](https://github.com/ansyaku/tabk.acl/blob/main/img/SQL1.png)
  <br><br>
* Pilih from PC
* Pilih delimited text file
* Definsikan pemisah, apakah koma
* Definsikan kolom
* Edit bila ada yang perlu diedit.
* Finish

## Koneksi SQL Server
***

Untuk koneksi dari ACL ke SQL Server, dapat dilakukan tahap-tahap berikut :
* Toolbar **Import** >> **Database and applications**<br><br>
  ![SQL1](https://github.com/ansyaku/tabk.acl/blob/main/img/SQL1.png)
  <br><br>
* Akan terlihat jendela, pilih **New Connection** . Pilih **ODBC Driver 17 for SQL Server**<br>.
* Akan muncul jendela, masukkan semua informasi yang dibutuhkan, nama server, username dan password. Klik **Ok**.
  <br><br>
  ![SQL1](https://github.com/ansyaku/tabk.acl/blob/main/img/SQL2.png)  
  <br><br>
* Akan muncul jendela, dari database yang ada pilih tabel-tabel mana saja yang akan diimpor, selanjutnya lakukan pengaturan yang sesuai dengan kebutuhan.
  <br><br>
  ![SQL1](https://github.com/ansyaku/tabk.acl/blob/main/img/SQL3.png)
  <br><br>
* Klik **Save**
* Data akan muncul pada ACL anda.
