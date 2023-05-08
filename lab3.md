# Lab Report 3: Researching Commands

## The `find` Command:

---
### Option 1: `-iname`
[Source](https://adamtheautomator.com/bash-find/), found by a Google search for the `find` command on the bash terminal.

The option `-iname` searches for a file or directory by name in a case insensitive manner. This option is helpful if you don't remember if the name of the directory or file is uppercase or lowercase ([ex. 1.1](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-11)). It is also helpful if the name of the directory or file is hard to type with the many differences in cases ([ex. 1.2](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-12)).

###### Example 1.1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -iname "TECHnical"
./technical
```

###### Example 1.2
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ mkdir ./technical/cAsE-iNseNsiTIVe

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -name "case-insensitive"

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -iname "case-insensitive"
./technical/cAsE-iNseNsiTIVe
```

---
### Option 2: `-maxdepth`
[Source](https://adamtheautomator.com/bash-find/), found by a Google search for the `find` command on the bash terminal.

The option `-maxdepth` can limit the amount of subdirectories in the search tree. This option can help find the directories or files with a limited number of directories so that there aren't as many options to look through. [Example 2.1](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-21) finds the directory technical with a maxdepth of 1, and [example 2.2](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-22) finds the text files with a maxdepth of 2 in `docsearch`.

###### Example 2.1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find . -maxdepth 1 -name "technical"
./technical
```

###### Example 2.2
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

---
### Option 3: `-type`
[Source](https://adamtheautomator.com/bash-find/), found by a Google search for the `find` command on the bash terminal.

The option `-type` can narrow the search down to a file or a directory, depending on whether you use f (file) or d (directory) after the command. In [example 3.1](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-31), `-type d` found all the directories and subdirectories in `./technical`. In [example 3.2](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-32), `-type f` found the files with `*.java` in its name.

###### Example 3.1
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

###### Example 3.2
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

---
### Option 4: `-delete`
[Source](https://adamtheautomator.com/bash-find/), found by a Google search for the `find` command on the bash terminal.

The option `-delete` can delete files and empty directories. As seen in [example 4.1](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-41), the directory cannot be deleted since it isn't empty, but the file can be deleted. The file, however, can be deleted, making `./technical/delete` now empty. Once empty, the directory can be deleted and no longer shows up under `./techincal` or under `-empty`, which can be seen in [example 4.2](https://aym-ie.github.io/cse15l-lab-reports/lab3#example-42).

###### Example 4.1
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ mkdir delete

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

###### Example 4.2
```
yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find "delete" -type d -delete

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ ls delete/
ls: cannot access 'delete/': No such file or directory

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ ls technical
911report/  biomed/  cAsE-iNseNsiTIVe/  government/  plos/

yeeam@AMY-XPS13 MINGW64 ~/Documents/GitHub/docsearch (main)
$ find -type d -empty
./.git/objects/info
./.git/refs/tags
```
