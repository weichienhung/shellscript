# create testing big file

`fallocate -l 1500M test.file`


# split file into multiple

`split -b 100m source.file -d -a 2 target.file_`

It will create  
target.file_00  
target.file_01  

-d means use digit number  
-a means length 2



