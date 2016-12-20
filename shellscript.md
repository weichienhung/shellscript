# pading zero digit

```
for (( i=0; i < 5; i++ )) ; do
		withPad=$(printf %02d $((i)))   # will ouptut 00 01 02 03 04
    
done
```
# show only even/odd line
```
sed -n 2~2p filename #even

sed -n 1~2p filename #odd
```
#  read line of the command result
```
sed -n 2~2p filename | while read -r line; do
        echo $line
done
```
# simple loop a array
```
myarray=( "test" "test2" "test3" )
for i in "${myarray[@]}"
do
  echo $i
done
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
