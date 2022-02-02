1.  grep command
```py
grep "Brian John" employees.txt

Brian John
Brian Johnson
```
But we need only Brian John not Brian Johnson
use the -w option

```py
grep -w "Brian John" employees.txt
Brian John
```
We need all Brian John's and avoid case sensitivity
use the option -i

```py
grep -wi "Brian John" employees.txt

Brian John
brian john
```
provide line number 
use the -n option
```py
grep -win "Brian John" employees.txt

26: Brian John
88: brian john
```
show certain number of the lines before the match
use the -B option

```py
grep -win -B 2 "Brian John" employees.txt
24:xyz
25:hij
26: Brian John

86:xyz
87:hij
88: brian john
```

show certain number of the lines after the match
use the -A option

```py
grep -win -A 2 "Brian John" employees.txt

26: Brian John
27:xyz
28:hij

88: brian john
89:xyz
90:hij
```

show certain number of the lines before and after the match
use the -c option

```py
grep -win -c 2 "Brian John" employees.txt
24:xyz
25:hij
26: Brian John
27:xyz
28:hij

86:xyz
97:hij
88: brian john
89:xyz
90:hij
```
Recursive Search(has performance issue for large set of directories and files)
The next line of code doesn't fetch records recursively
```py
grep -win "Brian John" ./*  or ./*.txt
```
we use the -r optoin to search recursivly
```py
grep -winr "Brian John" ./

grep -winr "Brian John" .
```
list only the files with the match inside
use the -l option

```py
grep -wirl "Brian John" .
```
list the no of matching records in each file
use the -c option

```py
grep -wirc "Brian John" .
```

##history

```py
history | grep "grep commit"
history | grep "grep commit"| grep "batch_id"

git commit ...batch_id...
git commit............................batch_id

```

get back all phone number records from emaployees file

```py
grep "...-...-...."  employees.txt
```

```py
grep "\d{3} -\d{3}-\d{4}" employees.txt

grep -p "\d{3} -\d{3}-\d{4}" employees.txt
```
use grep - v option to find the version of grep installed

```py
grep -v 
grp(BSD grep) 2.5.1 Free BSD

```
gnus is for linux - you can install it to mac
brew install grep --with-default-names