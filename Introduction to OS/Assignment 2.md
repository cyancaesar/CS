1: Finding all file that has the name `passwd` under `/etc` and redirecting `stderr` to `/dev/null`:
```bash
find /etc -name "passwd" 2> /dev/null
```

2: Finding all file under `/usr/share` that are greater than `5MB` and less than `10MB` and copying it to `/tmp/FILES`:
```bash
mkdir /tmp/FILES ; find /usr/ -size +$((5*1024*1024))c -size -$((10*1024*1024))c -exec cp -t /tmp/FILES/ {} \;

mkdir /tmp/FILES ; find /usr/ -size +5M -size -10M -exec cp -t /tmp/FILES/ {} \;
```

3: Adding current directory to environment variable
```bash
export PATH="$PATH:`pwd`"
```

Redirecting both `stdout` and `stderr` to a file

```bash
ls -l /*/* &> stdouterr.txt                                                              
```

Print the number of files on the current directory 

```bash
# ls . -l | grep -v "^d" | grep -v "^total" | wc -l
# ls . -l | grep "^-" | wc -l

echo "There are `ls . -l | grep "^-" | wc -l` files in this directory"
```