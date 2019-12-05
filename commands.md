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

# show duplicates line in two files
The files must be sorted  
`
comm -1 -2 {file1} {file2}
`

# Sort data
```
sort -t `echo -e '\001'` -k 1,1 -k 3,3r test.file

# -t means separator. here is CTRL+A
# -k means sort by column 1 and column 3. r means reverse sorting (descending)
# test.file is source.
```

# sed tutorial
## retrieve the specified string from a line  
for example a xml file
```
<myxml>
  <release>1.0.22</release>
</myxml>
```
To get release version
```
latest=$(cat my.xml | sed -n 's/.*<release>\(.*\)<\/release>/\1/p')
# (, ), / is special characters. add prefix '/'
# \1 to get group 1 result
```

## replace string in a config file
```
sed -i 's/.*MyTest.*/YourTest/' config.txt
```

## insert a new line in a config file
```
sed -i 's/.*MyTest.*/&\nYourTest/g' config.txt
```

### sed delimiter can be changed. like
```
sed -i 's:.*MyTest.*:YourTest:' config.txt
```

## show only even/odd line
```
sed -n 2~2p filename #even

sed -n 1~2p filename #odd
```

##  read line of the command result
```
sed -n 2~2p filename | while read -r line; do
        echo $line
done
```

# show real disk usage
`du -Ssbh`
