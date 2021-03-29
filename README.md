# Mobile AL Data Layer

This library provides a data layer to interact with Mobile AL data files in CSV format. It allows
for reading and writing data in a CSV file to Python lists and dictionaries. It provides some
functions similar to the normal Python file object, such as `open()` and `close()` methods and
the ability to use it as a context manager and iterator to loop through rows in the file.

## CSV Data Format

The code expects files to be in CSV format, with the first two rows being header rows:
First: List of comma-separated field names
Second: List of comma-separated field types matching the names in the previous row. Types:
 - `dt`: a datetime object
 - `f` : a float
 - `s` : a str

All other rows following must be the same number of items as the headers. (Any missing data
should be represented by an empty slot. In other words, there should be the same number of
commas on every line.) Each value is converted to the type specified for its column when
read.

Example:

```
stamp,x,y,label
dt,f,f,s
2020-03-24 15:00:00.0000,1.0,-7.3,Example
2020-03-24 15:00:00.2000,0.7,,
```

## Dependencies:
None. Though only tested in newer versions of Python 3 so you may experience issues with older
versions (e.g. before Python 3.5).
