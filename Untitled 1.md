```bash
count=1

for file in *.ext1; do
    mv "$file" "Filename-${count}.ext2"
    ((count++))
done
```


