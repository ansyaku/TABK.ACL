# Sorting, Filtering, Searching
***

## Sorting
Quick sort sort the values in a column to temporarily reorder the records in a view
Sort command sort records and output them to a new, physically reordered Analytics table
Index command index records to temporarily sort them in the current table
Presort sort records as an integral part of the execution of an Analytics command

## Filtering
* Quick filter digunakan untuk memfilter data menggunakan mouse dalam suatu view.
* Global filter restrict which records in a view are displayed, or processed by Analytics operations
* Local filter restrict which records are processed during a single execution of a single Analytics operation

### Global filters (view filters)
Filter global berfungsi untuk memfilter baris-baris pada tampilan yang sedang ditampilkan atau diprose.

#### Filter sederhana (Simple Filter)
Hanya satu kriteria, misalkan 
* yang namanya si anu
* yang tanggal lahirnya 21/05/1999
* yang npwpnya 01.061.173.9-051.000

#### Filter kompleks (Complex Filter)
lebih dari satu kriteria
Contoh : 
* yang namanya si anu dan tanggal lahirnya 21/05/1999 dan npwpnya 01.061.173.9-051.000
You can apply only one filter at a time to a view, but as the example above shows, you can use Boolean operators such as AND and OR to combine multiple criteria in a single filter. For more information about Boolean operators, see Operators in Analytics expressions.


Include records if ALL values are matched
Include records if ANY values are matched
Include records if ALL values are NOT matched
Include records if ANY values are NOT matched


## Partial matching
Partial matching is supported when filtering character data – that is, the filter value can be contained by a longer value in the field you are using for filtering.

For example:

Vendor_Name = "R" restricts a table to vendors with names beginning with “R”.
Address = "PO Box" restricts a table to addresses that start with “PO Box”.
Note

Filter values must appear at the start of fields to constitute a match.

Partial matching is enabled when the Exact Character Comparisons option is off (the default setting). If the option is on, partial matching is disabled and the filter value must exactly match a value in a field to constitute a match. For more information, see Table options.

## Filter retention

You can make a global filter the default filter for a table so that it is automatically applied every time you open the table.
* Filter global tetap aktif sampai anda menghapusnya, mengganti dengan filter global lain, atau menutup tabel. Apabila filter global aktif, maka indikator filter global akan muncul pada status bar followed by the filter syntax or the filter name, depending on whether the filter is ad hoc or named.
* Filter global berbeda dengan filter lokal. Filter lokal hanya aktif pada saat satu proses analitik.

#### Different ways to create and apply a global filter
There are several different ways to create and apply a global filter:
* Manually enter the filter syntax in the Filter text box
* Create a quick filter
* Create a filter, or select an existing filter, using the Expression Builder
* Select an existing filter from the Filter drop-down list

Quick sorting data in a view
Quick filtering data in a view
Quick searching data in a table
Sorting and indexing
Filtering data
Searching data
Search and filter using Analytics functions

## Quick filtering data in a view
* Quick filter juga bisa diberi nama dan disimpan untuk penggunaan di waktu lain. Quick filter dapat dilakukan dengan menggunakan mouse. 
Anda bisa memilih satu nilai
![Quick Filter](https://github.com/ansyaku/tabk.acl/blob/main/img/QuickF1.png)
atau beberapa nilai sekaligus namun harus berdekatan. Quick filters merupakan filter global 
![Quick Filter](https://github.com/ansyaku/tabk.acl/blob/main/img/QuickF2.png)
* Quick filtering hanya dapat digunakan untuk dua nilai yang bersebelahan. Jadi, apabila berniat untuk melakukan filter dengan kolom berjauhan, atur terlebih dahulu kolom pada viewnya agar letaknya bersebelahan atau bisa juga dengan menggunakan Expression Builder. Opsi lain, bisa juga dengan menggunakan dua tahap, quick filter pertama dan kemudian quick filter ke dua..


## Quick filtering by blank or non-blank values
Two of the options for quick filtering character fields are Blank and Not Blank. To use either of these criteria, you must first select a value in the field, but the actual selected value is ignored. This behavior allows you to filter a very long column of data for blanks without having to first locate a blank value.

### Menyimpan QUick Filter
Untuk menyimpan quick filter, klik Edit View Filter di toolbar, kemudian masukkan nama, klik OK.

## Filtering table data
Use filters to define precise data sets that are displayed in the table you are working with. As you work with filters, any associated visualizations or metrics update to reflect the filtered data.

Example
You are working with a table of customer data and you want to only look at customers in New York with a credit limit exceeding $50,000. To filter the table so that only these customers are displayed, you create the following filters:

STATE = NY
LIMIT > 50000

## Searching

Quick search find a word, a phrase, a number, or a date in a table
Isolate all matching records perform simple or advanced searches to include only records that match the search criteria
Select the first matching record select the first record in a table that matches the search criteria
You can enter one or more search terms in the Filter text box at the top of the View tab to perform a quick search of the data in a table.

With sorting and filtering, you also have the option of performing these operations as an integral part of the execution of other Analytics commands. 
For example, to summarize only third quarter transactions in an annual table, you could incorporate a date filter in the summarize command.
All the source data in the table is searched, not just the data displayed in the current view. For information about source data, tables, and views, see The structure of Analytics tables.

Entire records are searched, including any undefined portion of the record, rather than specific fields. For example, entering casino finds records that contain “casino” anywhere in the record. You can subsequently modify the search if you need to search a specific field (character data searches only).

Computed fields and related fields are not searched unless you subsequently modify the search to specify the specific field.

Data types searched
Searching character data is the most straightforward use of quick search. You can also search numeric and datetime data, however there are some additional considerations to take into account, explained in subsequent sections.

Searching data
You can use different methods for searching data in Analytics tables:
|Hasil yang Ingin Ditampilkan |Metode|
|-----|--------|
|Ambil seluruh baris yang memenuhi |Filter textbox       |
|Ambil baris pertama yang memenuhi |Kotak Search     |

Tip
Typically, users search to isolate all matching records, which returns a set of results. So normally you use the Filter text box and you can ignore the Search dialog box.

Searching to isolate all matching records
Basic search
To perform a basic search, enter an expression in the Filter text box at the top of a table view and press Enter.

The example below isolates all records that contain the name “United Equipment” in the Vendor_Name field:

Pencarian sederhana
![Contoh1](https://github.com/ansyaku/tabk.acl/blob/main/img/Search1.PNG)

Mencari dengan menggunakan relasi AND
![Contoh1](https://github.com/ansyaku/tabk.acl/blob/main/img/Search2.PNG)

Mencari dengan logika bolean ">="
![Contoh1](https://github.com/ansyaku/tabk.acl/blob/main/img/Search3.PNG)

Apabila pencarian cukup kompleks, jangan gunakan searching, tapi gunakan metode quick filter atau advance searching dengan menggunakan fungsi. 

### Search for blank, empty, or invalid values
You can search for blank text or numeric values, or blank or invalid datetime values. You can search for non-blank values by changing the operator you use in the expression.

Untuk teks:
1. Mengambil seluruh baris dimana **Vendor_Name** kosong: ISBLANK(Vendor_Name)
2. Mengambil seluruh baris dimana **Vendor_Name** tidak kosong: NOT(ISBLANK(Vendor_Name))

Untuk numerik
1. Mengambil seluruh baris dimana **Invoice_Amount** kosong: Invoice_Amount=0
2. Mengambil seluruh baris dimana **Invoice_Amount** tidak kosong: Invoice_Amount<>0

Untuk tanggal/waktu:
Untuk numerik
1. Mengambil seluruh baris dimana **Invoice_Date** kosong: NOT VERIFY(Invoice_Date)
2. Mengambil seluruh baris dimana **Invoice_Date** tidak kosong: Invoice_Date<>0; Invoice_Date <> `19000101 VERIFY(Invoice_Date)

## Guidelines for basic searches
Field names	
You must specify a field name to search in, and it must be the physical field name in the table layout, not the display name in the table view.

**Notes:** <br>
Untuk melihat nama fisik dari sebuah kolom, klik kanan pada header kolom, kemudian pilih **Properties**.

Untuk melakukan pencarian pada lebih dari satu kolom, bisa dilakukan dengan membuat perintah yang melakukan pencarian pada lebuh dari satu kolom. Namun, carra lain untuk melakukannya adalah dengan menggunakan fungsi (Analytics functions).
Partial matching	Partial matching of search terms is not supported.

Peraturan : <br>
1. Untuk mencari teks, gunakan petik buka dan petik tutup. Contoh: "Makanan" 
2. Untuk mencari tanggal, gunakan back quotes. Contoh: '19990530'	Pencarian tanggal harus dalam format YYYYMMDD atau YYMMDD.
3. Untuk mencari waktu, gunakan format hhmmss dan dimulai dengan satu spasi kosong dan satu huruf ‘t’ atau ‘T’. Misalkan: `t183000`
4. Jangan gunakan slashes (/) or colons (:) between the individual components of dates or times.

Related fields	To search in a related field you must specify the fully qualified field name: table name.field name.

## Quick search and quick filter
Quick search and quick filter are two Analytics features that make searching easier by building the search expression for you in the Filter text box.
Quick search you enter a text term in the Filter text box
Quick filter you use the mouse to select search criteria
Some limitations exist with quick search and quick filter, which are explained in the topics about these features.

Search using Analytics functions
Using functions to search gives you the greatest degree of power and flexibility. Similar to a basic search, you enter a search expression in the Filter text box, but the expression contains a function.

The example below uses the FINDMULTI( ) function to isolate all records that contain at least one of the search terms anywhere in the record.



For detailed information about searching using functions, see Search and filter using Analytics functions.

Select the first matching record
You can use an Analytics command, accessed from the main menu, to select the first record in a table that meets the search criteria. This capability is primarily useful in Analytics scripts, where it can be used in conjunction with other commands to perform certain tasks.

One of the commands allows you to go directly to a specific record number, which can be helpful in the Analytics user interface when navigating large tables.

For more information, see Selecting the first matching record
Automatic conversion of search term to a filter
The search term or terms you enter are automatically converted to a global filter that uses the FIND( ) function.
For example, entering casino results in the filter FIND("casino").
The filter auto-populates the Filter text box, from where you can modify it, if required. For example, you could modify FIND("casino") to limit the search to a specific field: FIND("casino", Merchant).

The filter is also added to the filter history and to the command log, from where you can subsequently reapply it.

Search terms and filter syntax automatically distinguished
The Filter text box automatically distinguishes between search terms and filter syntax. For example, entering match in the Filter text box searches for the character string “match”, whereas entering match(City, "New York", "Washington") creates a filter using the MATCH( ) function.

Steps
Note

When searching for numbers or datetime values, you need to match the source data formatting rather than the formatting in the view. For more information, see Quick searching numeric or datetime data.

Search for one or more search terms
In the Filter text box at the top of the View tab, type one or more search terms and press Enter.

With multiple search terms, the quick search performs a logical OR operation and finds records that contain at least one of the search terms.

Search for an exact phrase
In the Filter text box at the top of the View tab, type the phrase, enclose it in double quotation marks, and press Enter.

The quick search finds only those records that contain the exact phrase.

Limit the search to a specific field (character fields only)
Modify the automatically generated filter in the Filter text box by typing a comma after the search term, and then add the name of the field.
For example, modify FIND("casino") to FIND("casino", Merchant).

Press Enter.
The search is restricted to the field that you specified.

Note

You must use the physical name of the field, which may not be the same as the display name of the field in the view.
Untuk melakukan 

To check the physical name, right-click the appropriate column header and select Properties. If necessary, copy the physical name from the text box at the top of the Modify Column dialog box. Do not use the Alternate Column Title.

To search in a related field you must specify the fully qualified name of the field (that is, table.field name). For example: FIND("casino", Vendor.Vendor_Name)

Quick searching character data
When quick searching character data, you can enter whole or partial words, or exact phrases.

OpenShow me more
If you enter more than one word, the quick search performs a logical OR operation and finds records that contain at least one of the words.
If you want to search for an exact phrase, enclose the phrase in double quotation marks.
To isolate a search term, include a trailing space after the term and enclose the term and the space in double quotation marks.
For example, "cash " returns “cash” but not “cashier”, assuming that in the data the string “cash” is followed by at least one space

Search terms

Return records that contain:

cas
casino
cash
Americas
Lancashire
etcetera . . .
casino
casino
casinos

casino liquor

casino

casinos

liquor

liquors

casino (and) liquor (order not considered)

etcetera . . .

“Diamond Casino”

Diamond Casino

“Diamond Casino” “Golden Casino”

Diamond Casino

Golden Casino

Diamond Casino (and) Golden Casino (order not considered)

casino, “ABC Liquors”

casino

casinos

ABC Liquors

casino (and) ABC Liquors (order not considered)

etcetera . . .

“ABC L”

ABC Liquors

ABC Limousine

ABC Learning

etcetera . . .

“cash ”

(the word ‘cash’ followed by one space)

cash

(in the data, requires that the string ‘cash’ is followed by at least one space)

does not return ‘cashier’ or ‘Lancashire’

Quick searching numeric or datetime data
Note

If you want to search for numeric or datetime data in a specific field, use quick filtering. For more information, see Quick filtering data in a view.

When quick searching numeric or datetime data, you need to remember that you are searching the underlying source data rather than the data displayed in a view.

Numbers, dates, and times are often formatted differently in the source data than they are in the view. Search terms need to match the source data formatting rather than the formatting in the view.

You can select Edit > Table Layout to view the source data for a table.

Quick searching numeric data
The numeric format in the source data affects which records are returned for a specific search term.

OpenShow me more
Search term

Numeric format in view

Numeric format in source data

Returns records that contain:

1234.00

9999.99

9999.99

1234.00

9,999.99

no records returned

1,234.00

9,999.99

9999.99

no records returned

9,999.99

1,234.00

9.999,99

no records returned

(1234.00)

(9999.99)

(9999.99)

(1234.00)

-9999.99

no records returned

1234.01

9999.99

(number rounded)

for example: 1234.01

9999.9999

for example: 1234.0085

no records returned

1234.0085

1234.0085

123 456

9999.99

9999.99

123

456

123 (and) 456 (order not considered)

Quick searching datetime data
The datetime format in the source data affects which records are returned for a specific search term.

OpenShow me more
Search term

Datetime format in view

Datetime format in source data

Returns records that contain:

12/31/2015

MM/DD/YYYY

MM/DD/YYYY

12/31/2015

DD/MM/YYYY

no records returned

YYYYMMDD

no records returned

31/12/2015

MM/DD/YYYY

no records returned

DD/MM/YYYY

31/12/2015

YYYYMMDD

no records returned

20151231

MM/DD/YYYY

no records returned

DD/MM/YYYY

no records returned

YYYYMMDD

20151231

2015-12-31

YYYY-MM-DD

YYYY-MM-DD

error message

no records returned

FIND("2015-12-31")

2015-12-31

23:59:59

hh:mm:ss

hh:mm:ss

23:59:59

hhmmss

no records returned

20151231.235959

MM/DD/YYYY hh:mm:ss

YYYYMMDD.hhmmss

20151231.235959

MM/DD/YYYY hh:mm:ss

no records returned

Additional characteristics of quick searching
Quick searching has these additional characteristics:

Characteristic	Description
Case-sensitivity	The search is not case-sensitive.
Wildcards	Wildcard characters in search terms are not supported.
Spaces	Leading, trailing, and intervening spaces in search terms are considered only if you enclose the search term or terms and the spaces inside double quotation marks.
When spaces are enclosed by double quotation marks they are treated like characters and must be exactly matched in the data.

Quotation marks	Only double quotation marks can be used for enclosing phrases. Single quotation marks are not supported for this purpose and are treated like a regular character.
Computed fields	Computed fields are not searched.
Related fields	Related fields are not searched.
Limiting search by field	When modifying the auto-populated filter to limit the search to a specific field you can specify only character fields.
Specifying a numeric or datetime field causes an error.

Unsupported characters	
If used in quick search terms, the following characters may give inconsistent results, or cause an error message, because they are the operators used in Analytics expressions:

^ * ( ) - + = < >

If you want to search for one of these characters, manually enter the FIND( ) function in the Filter text box. For example:

FIND("a+b") or FIND("2015-12-31")

Field boundaries
Trailing spaces

Field boundaries in records are ignored, which means it is possible for a search term to match a string of characters across a field boundary. Trailing spaces in fields are treated like characters.
Search results found across field boundaries may not be valid results, unless you specifically intend this type of search. For example, the last digits of an account number and the first digits of an amount in an adjacent field could match a numeric search term, but would probably be a false positive.

Note

The field boundaries under discussion are the ones that appear in the table layout, based on the physical order of fields in the layout.

The order of fields in the layout can differ from the order of columns in the associated view, creating different adjacencies in the layout and the view.

If it is unclear why quick searching is returning a particular record, select Edit > Table Layout to view the source data being searched.

Additional searching and filtering information
For many other data searching options, including using wildcards, see Searching data.
For more information about filtering, see Filtering data.
For more information about the FIND( ) function, see FIND( ) function.


Search and filter using Analytics functions
You can use Analytics functions to perform powerful and effective searching and filtering of data in tables.

To use a function to search or filter, you create a filter in the Filter text box at the top of the table view. The filter uses one of the Analytics functions explained below.

For example, this filter uses the FINDMULTI( ) function to isolate all records that contain at least one of the search terms anywhere in the record:



Guidelines for searching or filtering using functions
Field names	
When you specify a field name to search in, it must be the physical field name in the table layout, not the display name in the table view.

Tip

To see the physical field name, right-click a column header in the table view and select Properties.

Quotation marks	Text search terms must be enclosed in "quotation marks".
Back quotes	Datetime search terms must be enclosed in `back quotes`.
Datetime format	
Datetime search terms must use YYYYMMDD or YYMMDD format.
Any time portion must use hhmmss format, and be preceded a single blank space, the letter ‘t’, or the letter ‘T’. For example: `t183000`
Do not use any separators such as slashes (/) or colons (:) between the individual components of dates or times.
Related fields	To search in a related field you must specify the fully qualified field name: table name.field name.
Function rules	
Each function has specific rules that govern how it works – things like supported data types, and case-sensitivity.

For a high-level comparison of the rules governing Analytics search functions, see A comparison of Analytics search functions. For detailed information about any function, click the linked function name below.

Types of searches
You can use a function to search or filter text, numeric, or datetime data. However, you need to use the right function for the type of data that you are searching or filtering:

Data type supported by a function Functions are designed to work with a specific data type, or in some cases they can work with more than one data type.
For example, you can use the ISBLANK( ) function with text data (character data) but not with numeric or datetime data. You can use the MATCH( ) or BETWEEN( ) functions with character, numeric, or datetime data.

Data type of the data You need to be aware of the data type of the data that you are searching or filtering and use a function appropriate for the data type. Numbers and dates typically have a numeric or datetime data type. However, they may be using a character data type.
Note

You can click any function name below for detailed information about the function.

Tip

You can copy and paste any of the examples below directly into the Filter text box, and modify the search terms and other inputs to match your data.

# Text searches (character data type)

## Mencari suatu kata/frase/kalimat

**Use: FIND( ) function**<br>
Description:<br>
Fungsi SEARCH tidak case-sensitive. Bisa digunakan untuk seluruh baris atau suatu kolom tertentu saja.
Contoh:<br>
1. FIND("United Equipment")
2. FIND("Equip")
3. FIND("United Equipment", Vendor_Name)
4. FIND("United Equipment", Vendor.Vendor_Name)

## Mencari nilai yang kosong
**Use: ISBLANK( ) function**<br>
Description: Allows you to search for blank values in a character field.
Contoh:
1. ISBLANK(First_Name)


## Search for multiple text terms
**Use: FINDMULTI( ) function**
Description: The same as FIND( ), but allows specifying multiple search terms.

Contoh:
1. FINDMULTI(RECORD, "United Equipment", "Muller Corp.")
2. FINDMULTI(RECORD, "equip", "supp")
3. FINDMULTI(Vendor_Name, "United Equipment", "Muller Corp.")
4. FINDMULTI(Vendor.Vendor_Name, "United Equipment", "Muller Corp.")

**Use: MATCH( ) function**
Description: A versatile search function that allows you to search a field for multiple search terms simultaneously, or search multiple fields for the same search term. Also allows you to find matching values in two fields.
Contoh: 
1. MATCH(Vendor_City, "Phoenix", "Austin", "Los Angeles")
2. NOT MATCH(Vendor_City, "Phoenix", "Austin", "Los Angeles")
3. MATCH(Product_Code, "A", "D", "F")
4. MATCH(Product_Code, "A", "D", "F")
The Exact Character Comparisons option must be on.
Note
MATCH( ) examples assume that the Exact Character Comparisons option is off, except where noted.

**Search for case-sensitive text terms**
Use: MATCH( ) function
Description: A versatile search function that allows you to search a field for multiple search terms simultaneously, or search multiple fields for the same search term. Also allows you to find matching values in two fields.

Contoh:
1. MATCH(Last_Name, "SMITH")
2. MATCH(Last_Name, "smith")
3. MATCH(Last_Name, "Smith")

**Search for a text term in multiple fields**
Use: MATCH( ) function
Description: A versatile search function that allows you to search a field for multiple search terms simultaneously, or search multiple fields for the same search term. Also allows you to find matching values in two fields.
Contoh :
1. MATCH("Phoenix", Vendor_City, City, City_2)
Isolates all records in which at least one of the values in the Vendor_City, City, or City_2 fields exactly matches, or begins with, “Phoenix”.

**Search for matching text terms**
Use: MATCH( ) function
Description: A versatile search function that allows you to search a field for multiple search terms simultaneously, or search multiple fields for the same search term. Also allows you to find matching values in two fields.
Example:
1. MATCH(Vendor_Address, Employee_Address)
Isolates all records with identical vendor and employee addresses.

You may need to use additional functions to standardize the format of vendor and employee addresses.

**Search for one or more occurrences of a specific character or substring**
Use: OCCURS( ) function
Description: Allows you to search for one or multiple occurrences of a substring in a character field.

OCCURS(Invoice_Number, "-") > 1
OCCURS(Full_Name, ALLTRIM(Last_Name))=1 Isolates all records in which the value in the Last_Name field appears in the Full_Name field. Including the ALLTRIM( ) function in the expression removes any leading or trailing spaces from the Last_Name field, ensuring that only text values are compared.
OCCURS(Vendor_Name, "UNITED EQUIPMENT")> 0
Isolates all records that contain the name “UNITED EQUIPMENT”, in uppercase, in the Vendor_Name field.

Unlike the FIND( ) function, the OCCURS( ) function is case sensitive.

### Search for a substring starting at a specific character position
Use: AT( ) function

Description: Allows you to search for a substring, or a subsequent occurrence of the substring, in a character field, and specify the starting byte position of the target substring.

Example

Result

AT(2, "-", Invoice_Number) > 10
Isolates all records in which the invoice number contains 2 or more hyphens, and the second hyphen occurs after the tenth character in the string.

### Search for text in a range
Use: BETWEEN( ) function
Description: Allows you to search for text values that fall within a range.
Example
Result
BETWEEN(Last_Name, "C", "K")
Isolates all records in which the value in the Last_Name field begins with one of the letters from “C” to “K”, inclusive.
The Exact Character Comparisons option must be off.

### Search for nearly identical text values (fuzzy duplicates)
Use: ISFUZZYDUP( ) function
Description: Allows you to search for nearly identical values (fuzzy duplicates), as well as identical values. Not case-sensitive.
Use: LEVDIST( ) function
Description: Similar to ISFUZZYDUP( ), but case-sensitive by default.
Example
Result
ISFUZZYDUP(Last_Name, "Braun", 2)
Isolates all records with the name “Braun”, or fuzzy duplicates of the name “Braun”, in the Last_Name field.
The Levenshtein distance (degree of fuzziness), set to 2 in this example, can be increased or decreased.
LEVDIST(TRIM(Last_Name), "Braun") < 3
Isolates all records with the name “Braun”, or fuzzy duplicates of the name “Braun”, in the Last_Name field.
The Levenshtein distance (degree of fuzziness), set to < 3 in this example, can be increased or decreased.
Including the TRIM( ) function in the expression removes any trailing spaces from the last name field, ensuring that only text values are compared.

### Search for a basic pattern
Use: MAP( ) function
Description: Allows you to search using wildcard characters, literal characters, or a mix of both.
Contoh: 
1. MAP(Invoice_Number, "XX99999")
2. MAP(Invoice_Number, "AB12345")
3. MAP(Invoice_Number, "AB99999")
4. NOT MAP(SSN, "999-99-9999")

### Search for a more complicated pattern
Use: REGEXFIND( ) function
Description: The most powerful and flexible search function. Allows you to search using regular expressions that combine literal characters and metacharacters. Can be more complicated to use than other search functions.
Contoh:
1. REGEXFIND(Vendor_City, "Phoenix|Austin|Los Angeles")
2. REGEXFIND(Product_Code, "\b\d{3}-[a-zA-Z]{6}\b")
3. REGEXFIND(Product_Code, "\b\d{3,}-[a-zA-Z]{6}")

## Numeric searches
### Search for a number
Use: MATCH( ) function
Description: A versatile search function that allows you to search a field for multiple search terms simultaneously, or search multiple fields for the same search term. Also allows you to find matching values in two fields.
Example
Result
MATCH(Invoice_Amount,154.00)
Isolates all records with an invoice amount of $154.00.
MATCH(Invoice_Amount,154.00, 522.00)
Isolates all records with an invoice amount of $154.00 or $522.00.
NOT MATCH(Inventory_Value_at_Cost, Cost_x_Quantity)
Isolates all records with different amounts in the Inventory_Value_at_Cost field and the computed Cost_x_Quantity field.


### Search for numbers in a range
Use: BETWEEN( ) function
Description: Allows you to search for numeric values that fall within a range.
Example
Result
BETWEEN(Invoice_Amount, 1000, 5000)
Isolates all records with an invoice amount from $1000 to $5000, inclusive.


### Search for a number throughout an entire table
Use: FIND( ) function
Description: Allows searching entire records in addition to searching an individual field or fields.
Use: FINDMULTI( ) function
Description: The same as FIND( ), but allows specifying multiple search terms.
Note
Using the FIND( ) or FINDMULTI( ) functions to search for a numeric value can be tricky. The functions search the exact characters in the source data file (.fil), which can be presented differently in the table view.
If search results seem inconsistent to you, examine the source data in the Table Layout dialog box.
Example
Result
FIND("154.00")
Isolates all records that contain the exact characters 154.00 anywhere in the record in the source data file.
Datetime searches

### Search for a datetime value
Use: MATCH( ) function

Description: A versatile search function that allows you to search a field for multiple search terms simultaneously, or search multiple fields for the same search term. Also allows you to find matching values in two fields.

Example

Result

MATCH(Invoice_Date, `20170731`)
Isolates all records with an invoice date of 31 Jul 2017.

MATCH(Invoice_Date, `20170731`, `20170831`, `20170930`)
Isolates all records with an invoice dated the last day of the month in each month of the third quarter.


### Search for blank or invalid date values
Use: VERIFY( ) function

Description: Allows you to search for blank or invalid values in a date field.

Example

Result

NOT VERIFY(Invoice_Date)
Isolates all records with a blank or invalid date in the Invoice_Date field.


### Search for datetime values in a range
Use: BETWEEN( ) function

Description: Allows you to search for datetime values that fall within a range.

Example

Result

BETWEEN(Invoice_Date, `20140930`, `20141030`)
Isolates all records with an invoice date from 30 Sep 2014 to 30 Oct 2014, inclusive.

NOT BETWEEN(Invoice_Date, `20140930`, `20141030`)
Isolates all records with an invoice date that does not fall between 30 Sep 2014 and 30 Oct 2014, inclusive.

Search for a datetime value throughout an entire table
Use: FIND( ) function

Description: Allows searching entire records in addition to searching an individual field or fields.

Use: FINDMULTI( ) function

Description: The same as FIND( ), but allows specifying multiple search terms.

Note

Using the FIND( ) or FINDMULTI( ) functions to search for a datetime value can be tricky. The functions search the exact characters in the source data file (.fil), which can be presented differently in the table view.

If search results seem inconsistent to you, examine the source data in the Table Layout dialog box.

Example

Result

FINDMULTI(RECORD, "31/07/2017", "31/08/2017")
Isolates all records that contain the exact characters 31/07/2017 or 31/08/2017 anywhere in the record in the source data file.

The normal restriction regarding datetime format (YYYYMMDD, YYMMDD, hhmmss, hhmm) does not apply when using FIND( ) or FINDMULTI( ) to search for a datetime value.
