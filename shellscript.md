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
