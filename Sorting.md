# Sorting, Filtering, Searching
***

## Sorting
Quick sort sort the values in a column to temporarily reorder the records in a view
Sort command sort records and output them to a new, physically reordered Analytics table
Index command index records to temporarily sort them in the current table
Presort sort records as an integral part of the execution of an Analytics command

## Filtering
Quick filter filter data by using the mouse in a view
Global filter restrict which records in a view are displayed, or processed by Analytics operations
Local filter restrict which records are processed during a single execution of a single Analytics operation


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

