# create testing big file

`fallocate -l 1500M test.file`


# split file into multiple

`split -b 100m source.file -d -a 2 target.file_`

It will create  
target.file_00  
target.file_01  

-d means use digit number  
-a means length 2

# count files under a folder

`find DIR_NAME -type f ¦ wc -l`

# Only show lines that's matched by a fiter file
For example: you have a source.txt and contains
```
AAA
BBB
CCC
DDD
AAA
DDD
GGA
BBB
DDD
KKK
```
And have a filter.txt contains
```
AAA
BBB
```
Below command to filter

`
cat source.txt | grep -f filter.txt
`


# Sort data
```
sort -t `echo -e '\001'` -k 1,1 -k 3,3r test.file

# -t means separator. here is CTRL+A
# -k means sort by column 1 and column 3. r means reverse sorting (descending)
# test.file is source.
```
