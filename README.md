# 42-Amman
# Shell

## Basic manipulation :
```bash
ctrl-a  # clear screen
pwd  #  (print working directory) writes the full pathname of the current working directory to the standard output.
cd  # change directory (cd .. to go back)
```

## Commands
### man (short for manual page) :
```shell
man name  # used to display the user manual of any command that we can run on the terminal
```
write /(slash) followed by a query to search in the man

### ls : 
```bash
ls  # (lists directory contents of files and directories) see file / folder
ls -a  # see hidden files
ls -al  # fileName	to have infos on the file
```
#### ls -l
see information / rights of the file
```bash
ls -l  # example -rwxr-x--x 1 thfavre 2022_lausanne 9 Aug 29 11:53 testShell00.txt 
``` 
Explication :
1) - : - for file, d for directory, l for links
2) thfavre can read, write and execute
3) 2022_lausanne can read not write and execute
4) the rest of the world can execute

### chmod : see information / rights of the file
```shell
chmod u+r fileName
# option 1 : u : user, g : group, o : other, a : all 
# option 2 : + to add, - to remove
# option 3: add the right of : r : read, w : write, x : execute

# to have rwx rw- r-- :  4+2+1 4+2+0 4+0+0 = 764 : donc 764 est pareil : 
chmod 764 fileName

chmod -h XXX  # to change the rights of the symbolic link itself rather than the file that the link point to
```



### tar : archive file 
#### Create
```shell
tar -cf fileName.tar fileName
tar -cf fileName.tar * 
```
#### Unarchive
```shell
tar -xvf fileName.tar
```

### file / folder management
```shell
mkdir folderName  # make directory (folder)
rmdir folderName # remove directory (should be empty)
rm -rf folderName  # also delete every file inside 

cat  fileName  # list the contents of a file
cat -e  # displays invisible characters

touch fileName  # create a file 
touch -t   201307150842 fileName  # changes the time
touch -ht 201307150842 linkName  # modifies the time of the link without changing the original
rm filename  # remove filename

#### Links
##### hard links : a hard link is like as an additional name for an existing file.
```

#### ln : Symbolic Links
##### Hard links
It is an additional name for an existing file.
```shell
ln folder1 folderName2  # create a copy link to the original (modifier )
```
##### Soft links
It is something like a shortcut in Windows. It is an indirect pointer to a file or directory.
```shell
ln -s folder1 linkFolderName  # linked file from folder 1 to linkFolderName 
```

#### Size of a file 
```shell
dd if=/dev/zero of=fileName bs=size count=1  # create a file of size size
# or write some character inside
```

### echo
  used to display messages, or to create and write to files
```shell
echo HEHEHE  # output HEHEHE
```

### cat
used to display a single line of text.
```shell
cat fileName  # -e to display invisible characters
```

### cp : copy
```bash
cp a b  # copy the a file to the b file
cp -R used to display a single line of text.
```

### find :
used to display a single line of text.
```
find startRepository
find startRepository -name text # find the file that contain text
# -type f  # f for file, d for directory
# -maxdepth Nb

```

### grep :
Search any line that contains the word in filename
```shell
grep 'word' filename  # -i : case insensitive, -R : looks also in all subdirectory, -c : display the number of time the word appears
```
