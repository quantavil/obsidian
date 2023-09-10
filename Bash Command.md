## File rename

This Bash command renames files from `.ext1` to `.ext2` with sequential numbering in the filename.

```bash
count=1

for file in *.ext1; do
    mv "$file" "Filename-${count}.ext2"
    ((count++))
done
```


```ba
```