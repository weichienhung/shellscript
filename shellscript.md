# pading zero digit

```
for (( i=0; i < 5; i++ )) ; do
		withPad=$(printf %02d $((i)))   # will ouptut 00 01 02 03 04
    
done
```
