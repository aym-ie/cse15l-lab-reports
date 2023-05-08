# Lab Report 3: Researching Commands

## The `find` Command:

---
### Option 1: `-iname`
[Source](https://adamtheautomator.com/bash-find/)

Example 1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -iname "TECHnical"
./technical
```
//


Example 2
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ mkdir ./technical/cAsE-iNseNsiTIVe

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -name "case-insensitive"

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -iname "case-insensitive"
./technical/cAsE-iNseNsiTIVe
```
//

---
### Option 2: `-maxdepth`
[Source](https://adamtheautomator.com/bash-find/)

Example 1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find . -maxdepth 1 -name "technical"
./technical
```
//

Example 2
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find . -maxdepth 2 -name "*.txt"
./basepair.txt
./biomed-sizes.txt
./find-results.txt
./grep-results.txt
./plos-sizes.txt
./technical/empty.txt
./text.txt
```
//

---
### Option 3: `-type`
[Source](https://adamtheautomator.com/bash-find/)

Example 1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find ./technical -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
//

Example 2
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ file > technical/empty.java
Usage: file [-bcCdEhikLlNnprsSvzZ0] [--apple] [--extension] [--mime-encoding]
            [--mime-type] [-e <testname>] [-F <separator>]  [-f <namefile>]
            [-m <magicfiles>] [-P <parameter=value>] [--exclude-quiet]
            <file> ...
       file -C [-m <magicfiles>]
       file [--help]

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find ./technical -type f -name "*.java"
./technical/empty.java
```
//

---
### Option 4: `-delete`
[Source](https://adamtheautomator.com/bash-find/)

Example 1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ mkdir delete

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ file delete/delete.txt
delete/delete.txt: cannot open `delete/delete.txt' (No such file or directory)

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ file > delete/delete.txt
Usage: file [-bcCdEhikLlNnprsSvzZ0] [--apple] [--extension] [--mime-encoding]
            [--mime-type] [-e <testname>] [-F <separator>]  [-f <namefile>]
            [-m <magicfiles>] [-P <parameter=value>] [--exclude-quiet]
            <file> ...
       file -C [-m <magicfiles>]
       file [--help]

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find "delete" -type d -delete
find: cannot delete ‘delete’: Directory not empty

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find "delete" -type f -delete

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -type d -empty
./.git/objects/info
./.git/refs/tags
./delete
```
//

Example 2
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find "delete" -type d -delete

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ ls delete/
ls: cannot access 'delete/': No such file or directory

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -type d -empty
./.git/objects/info
./.git/refs/tags
```
//
