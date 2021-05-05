# LINUX WEEK 9 (04-05-2021)
## Notes
### Two Ways to Execute File in Linux
1. Use absolute path like `/usr/bin/date`
2. Use relative path like `./runme`

to execute the file in relative path we need to add `./` before the filename to make sure that we want to run this file. So if there is a file named "ls" and you want to run it, you can type `./ls` so it will execute the "ls" file and wont execute the `ls` command that would list files and directory.

### Command to Find Certain File in Linux
1. `$ which` : this command only can be use to find executable files.
2. `$ locate` : this command use the database to search for the file. Before running this command it's important to update database by execute `$ updatedb` command to make sure that all the files have been included to database.
3. `$ find` : this command would search for the file by accessing the harddisk directly so this command need more time to run it. But this command has more features that would be useful in finding the file. We can set to find the file with size above 5MB, or with change mode time within 7 days, etc.

<br>

## Command
### 1). Edit file content in terminal
You can use the following command to edit the file content in terminal
```
$ cat << EOF > output.txt
```
EOF means end of file, to end editing the file simply type EOF in your terminal

<br>

---

<br>

### 2) Find file using find command
Find is a command that will directly access your disk to find the file, so it takes more time but it has some feature that could be used. Here is the example for find command :
```
$find /home -name install
```
from the command above :
1. `/home` is the directory to start searching for the file
2. `-name` is the test to tell the program to only search for the file that named "install". There are so many other expression that could be use.

You also can find the hidden file by type the following command :
```
$ find /home/user/ -type f -name ".*"
```

To read more, refer to this website [computerhope.com](https://www.computerhope.com/unix/ufind.htm).

<br>

---

<br>

### 3). Show disk usage
use the command below to check the disk usage for partition
```
$ df
```
while to calculate disk usage for directory can use the following command 
```
$ du -h -s [directory]
```

parameter:

`-h` will show size in byte instead of 1K-blocks.

`-s` for summary, this will make the output only show the final result and skip the detail information.

<br>

---

<br>

### 4). Word Count
to see the total lines, words, and characters from a file can use the following command:
```
$ wc
```
parameter :

`-l` for line

`-w` for word

`-c` for character

<br>

---

<br>

### 5). Compress and extract file in Linux
To compress file in Linux can use the following code

```
$ tar czvf backup.tar.gz *
```
"*" means all files in the current working directory, so the above command would compress all files in current working directory and name the compressed file as "backup.tar.gz".

While to extract the compressed file you can use the code below

```
$ tar xvfz backup.tar.gz
```