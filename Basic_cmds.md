1.  General purpose commands

1.1. Diplay Current user

 ```py
whoami
 ```
 Display list of logged in users
 ```py
who
 ```

1.2.   <span style="color:green;font-weight:500; font-size: 20px; font-family:Tahoma"> Display user id and group id details of current user
</span>

 ```py
 id
 ```
1.3.  Display date and time
 ```py
 date
 ```
 Date formats
 | symbol | Description|
 |-------|-------------------------------|
 | %d | Display the day of the month(01 to 31) |
 |%h| deplays abbreviated month name (Jan to Dec)|
 |%m|Displays the month of the year(01 to 12)|
 |%Y|Displays four-digit year|
 |%T|Displays the the time in 24 hour format HH:MM:SS|
 |%H|Displays the the hour|

 1.4.   List files and directories
 ```js
 ls
 ```
List of files and directories in the current directory
 ```py
 ls
 ```
list all files in the [/bin] directory
```py 
ls /bin 
  ```
list all files starting with b in the /bin directory.
```py 
ls /bin/b*
  ```

list all files ending with r in the /bin directory
```py 
ls /bin/*r
  ``` 
1.5.    Basic Information aobut OS
```py 
uname
  ``` 
using **-a** option prints all the system information in the follwoing order kernerl name, network node hostname, kerner release date, kernel version, machine hardware name, hardware platform, operating system.
```py 
uname -a
  ```
1.6.    infromation about active processes
```py 
ps
  ```
ps lists the processes that are currently running and their PIDs(process ids) and the out put containes the processes that are owned by you
-e option displays all the processes running and owned by other users as well.
```py 
ps -e
  ```
1.7.    Detail on the running processes and system resources
```py 
top
  ```
using top we can find which process is consuming the most resources 
M - sort by memory usage
P - sorto by CPU usage
N - sort by process ID
T - sorty by running time
```py 
top -n 10
```
1.8.    Display Message
```py 
echo
  ```
echo command displays the given text on the screen
```py 
echo "linux for TDM"
  ```
special charactors
|Special Character| Description|
|-----------------|-------------
|\n |new line|
|\t|tab|
1.9.    Download file from the internet
```py 
wget
  ```
the wget command help you download a file from the internet
```py 
wget [options] url
-O option sets the output file name
-b can be used if you want to download a very large file and close your connection to the server
-i if you want to download multiple files and you can create a text filw with the list of target files
  ```
1.10.   view reference manual
man command displays the user manual of the command given as argument 
```py 
man
  ```
  eg.
  ```py 
man ls
  ```
2.0.    Directory Management Commands
2.1. Name of your current directory
 ```py 
pwd
This will print /home/project.
  ```
2.2.    create a directory
 ```py 
mkdir
mkdir creates a new directory
  ```
```py 
mkdir myfolder
create a directory called myfolder in your current directory 
use the ls command to verify if the myfolder direcoty got created
  ```
2.3. change your current working directory

 ```py 
cd
if you use cd without any directory name it will move you back to your home directory
  ```
  ```py 
cd myfolder
use the pwod command to verify if the current working directory has changed
  ```
  ```py 
cd ..
use the command above to move to the parent directory. .. is a short cut that refers to the parent directory of your current directory
  ```
2.4.    Get a list of files in a directory
  ```py 
ls
ls -l prints a long list of files that has additional information
  ```
|Option| Description|
|-----------------|-------------
|-a |list all the files including hidden files|
|-d|list directories themselves not their content|
|-h|with -l and -s , print sizes like 1k,234M,2G etc|
|-l|long listing of files which include information about permission,owner,size etc|
|-F|classify files by appending type indicator like *,/etc, to file names|
|-r|reverse order while sorting|
|-S|sort by file size, largest first|
|-t|sort by time, newest first|

```py
ls -la /etc
get long listing of files in /etc folder including hidden files if any.
```
```py
ls -lt
to list files based on modification time and most recently modified file will be on top
```
```py
ls -ls
to get files sorted by file size in descending order
ls -lrs
to get files sorted by file size in ascending order 
```
2.5.    Delete directory 
```py
rmdir
rmdir removes a directory
```
Create a directory in the /tmp folder
```py 
mkdir /tmp/dummy
 ```
Verify by using the **ls** command
```py 
ls /tmp
 ```
 * Before removing any direcotry make sure you don't have any files or sub directories.
 Delete the dummy directory
 ```py 
rmdir /tmp/dummy
verify by using ls command
ls /tmp
 ```
2.6.    Search and locate files

```py 
find
Is used to search for files in a directory using file name,file type, size , timestamp etc.
 ```
* The following command finds all txt files in the subfolders of the /etc directory.
 ```py 
find /etc -name '*.txt'
 ```

 2.7.   Display the amount of disk space available on file systems

 ```py 
df
displays the information of the device name,total blocks, total disk space, used disk space, available disk space and mount point on a file system.
 ```
 ```py 
df
without any argument the command shows the information for all currently mounted file systems
df -h
-h option is used to view the disk space usage in human readable format. i.e in megabyte ,gigabite etc.
 ```
 3.    File Management
 3.1 Display file content
 ```py 
cat
cat command dispalys contents of files
 ```

 * The following command dispalys the content fo the file text.txt 
 ```py 
cat text.txt
 ```
 3.2    Display file contents page-wise

 ```py 
more
The more command displays the file contents page by page
press spacebar to display the next page
more text.txt
 ```
 3.3    Display first few lines of a file

 ```py
head
print the first 3 lines of the file text.txt.
head -3 text.txt
 ```
 3.4    Display last line of a file

 ```py 
tail
print the last 10 lines of the file text.txt
tail text.txt
you can specify the number of lines to be printed
tail -2 text.txt
 ```
 3.5    copy files

 ```py 
cp
 ```
 *copy text.txt into a file named text-backup.txt
 ```py 
cp text.txt text-backup.txt
 use ls command to verify the copy was successfull.
 ```
* The following command copies the content of /myfolder/employee to a file named 'HR.txt' under the current directory
```py 
cp /myfolder/employee hr.txt
use ls command to verify the copy was successful
 ```
 3.6     Move, rename a file.
  ```py 
mv
move command moves a file from one directory to another.
if the source adn target directories are the same, it works like rename operation.
 ```

 ```py 
mv test.txt as test-backup.txt
use ls command to verify
 ```

  ```py 
move to temp directory
mv test-backup.txt /tmp
use ls command to verify
ls -l /tmp
 ```
 3.7 create empty file
  ```py 
touch
 ```
 * Create an empty file named file.txt
  ```py 
touch file.txt
use ls command to verify
ls -l
 ```
 3.8 Remove files
  ```py 
rm
 ```
 * The rm command is ideally used along with the -i option , which makes it ask for confirmation beofore deleting.
 * Press y to confirm deletion or n to cnacel
 3.9 Create and manage file archives
  ```py 
tar
tar command allows you to copy multiple file and directories into a single archive file
 ```
 * The following command creates an archive of the entire '/bin' directory into a file named bin.tar.
 
 | Option | Description |
 |----|---|
 |-C|creates new archive file|
 |-v| Verbosely list files processed|
 |-f|Archive file name|
  ```py 
tar -cvf bin.tar /bin
 ```
  ```py 
tar -tvf bin.tar
To see the list of files in the archive, use -t option.
 ```

   ```py 
tar -xvf bin.tar
to untar the archive or extract files from the archive, use -x option.
use ls command to verify that the folder bin is extracted
 ```
3.6  Package and compress archive files
```py
zip
zip command allows you to compress files
 ```
```py
zip config.zip /etc/*.conf
creates a zip named config.zip with all the files with .conf extension in the /etc directory.
 ```
```py
zip -r bin.zip /bin
-r option can be used to zip the entire folder and creates an archive of teh '/bin' direcotry 
 ``` 
3.10    Extract, list or test compressed files in a zip archive
```py
unzip
 ```

 ```py
unzip -l config.zip
Extracts all the files in the archive 'config.zip'
 ```
```py
unzip bin.zip
extracts all the files in the archive bin.zip. 
You should see a folder named bin created in your directory
 ```
4.  Access Control Commands

|Permission|Symbol|
|---|----|
|read|r|
|write|w|
|execute|x|
* To see the permission set for a file run **ls -l** command

```py
ls -l test.txt
You can see the permission for a file named 'test.txt' in your current directory.
out put
-rw-r--r-- 1 Dani Dani 1024 June 4 22:20 test.txt
 ```
 Permission 'rw-r--r--'
 owner has read and write permission , group owner has read permission and others also have read permission.
4.1 chmod
chmod command lets you change the permission set for a file.
|Option|Description|
|-----|---|
|r, w and x|read, write and execute|
|u,g and O|owner, group and others|
|+, -| grant and revoke operations|

* The command below removes read permission for all (user,group and other) on test.txt.

```py
chmod -r test.txt

verify the changes

ls -l test.txt
 ```

 * Add read access to all on test.txt
```py
chmod +r test.txt
verify the changes
ls -l test.txt
 ```
 * Remove read permission for others
 ```py
chmod o-r test.txt
verify the changes
ls -l test.txt
 ```
 5. Text processing commands
 ```py
wc
 ```

  ```py
wc test.txt
find the number of lines, words and characters in the test.txt file.
 ```

  ```py
wc -l test.txt
find the number of lines in the test.txt file.
 ```
  ```py
wc -w test.txt
find the number of words in the test.txt file.
 ```
  ```py
wc -c test.txt
find the number of characters in the test.txt file.
 ```

5.2 Perform search operations within the text.
```py
grep
allows you to spesify patterns and search lines matching the pattern from the input text.
 ```
```py
grep quadrant test.txt
print all lines which contain the word quadrant in the test.txt file
 ```
|Option|Description|
|---|---|
|-n|along with the matching lines , print the line numbers also|
|-c|get the count of matching lines|
|-i|ignore the case of the test while matching|
|-v|print all lines which do not contain the pattern|
|-w|match only if the pattern matches whole words|

```py
grep -c -i GroWTH test.txt
find the total number of counts of the word growth in the test.txt file and ignore the case of the text
```

6.  Networking commands
6.1 Show the system's host name
```py
hostname
```
```py
hostname -i
You can use the -i option to view the IP address of the host
```
6.2 Test if a host is reachable
```py
ping
```
```py
ping www.google.com
check if www.google.com is reachable.
press ctrl+c to stop
```
```py
ping -c 5 www.google.com
Use -c option to ping only for a limited number of times
```
6.3 Display network interface configuration
```
ifconfig
configure of displays network interface paramenter for a network or entire adapter
```
```
ifconfig eth0
eth0 is usually the primary network interface that connects your server to the network
```
6.4. Transfer data from or to a server
```
curl

Access the file at the given url and display the contents on the screen.
```

