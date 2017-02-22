# repackt
- The
[Packtpub](https://www.packtpub.com/)
epub file renamer

You can get a free book daily from
[Packtpub](https://www.packtpub.com/)
[here](https://www.packtpub.com/packt/offers/free-learning)

The problem is that they name the file with a strange number (most
likely an inventory index or similar)

So I created this script to rename the files so that they are easier to
find in a folder full of similarly named epubs.  It works by zgrep'ing
for the title field in the `.ocf` file

### Usage

##### list

repackt list $STRING - show all files that have $STRING in their name

##### dry

repackt dry $STRING - dry run show the moves that would take place for all files that have $STRING in their name

##### epub

repackt epub $STRING - rename all files that have $STRING in their name

### Example Usage

```
repackt epub 978
```

this will move a file called 978132434345.epub to TheProperTitle.epub and any other files which match the $STRING

##### list

```
➜  Backt ./repackt list 978
-rw-r--r-- 1 user user 8.6M Feb 20 22:27 97812345678.epub
-rw-r--r-- 1 user user 583K Feb 20 22:27 97812345678_code.zip
```

##### dry

```
➜  Backt ./repackt dry 978
mv 97812345678.epub MasteringLinuxShellScripting.epub
mv 97812345678_code.zip MasteringLinuxShellScripting.code.zip
```

##### epub

```
➜  Backt ./repackt epub 978
-rw-r--r-- 1 thoth thoth 8.6M Feb 20 22:27 97812345678.epub
mv 97812345678.epub MasteringLinuxShellScripting.epub
mv 97812345678_code.zip MasteringLinuxShellScripting.code.zip
-rw-r--r-- 1 thoth thoth 583K Feb 20 22:27 MasteringLinuxShellScripting.code.zip
-rw-r--r-- 1 thoth thoth 8.6M Feb 20 22:27 MasteringLinuxShellScripting.epub
```

###### To do
   implement renamers for `mobi` and `pdf` as well
