# write Ctrl+A in script. more portable
```
CTRL_A=`echo -e '\001'`
cut -d $CTRL_A .....
awk -F $CTRL_A .....
```

# pading zero digit
```
for (( i=0; i < 5; i++ )) ; do
		withPad=$(printf %02d $((i)))   # will ouptut 00 01 02 03 04
    
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
