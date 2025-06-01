# lsof Command Examples

**lsof** or **‘LiSt Open Files’** is used to find out which files are open by which process. Since **[[Linux]]/Unix** considers everything as a files (**pipes**, **sockets**,**directories**, **devices** etc) we can use this command to identify which files are currently in use.

## List all Open Files with lsof Command

In the below example, it will show long listing of open files some of them are extracted for better understanding which displays the columns like **Command**, **PID**, **USER**, **FD**, **TYPE** etc.
![[Pasted image 20230712231143.png]]

Sections and it’s values are self-explanatory. However, we’ll review **FD & TYPE** columns more precisely.

**FD** – stands for File descriptor and may seen some of the values as:

1. **cwd** current working directory
2. **rtd** root directory
3. **txt** program text (code and data)
4. **mem** memory-mapped file

Also in **FD** column numbers like **1u** is actual file descriptor and followed by u,r,w of it’s mode as:

1. **r** for read access.
2. **w** for write access.
3. **u** for read and write access.

**TYPE** – of files and it’s identification.




1. **DIR** – Directory
2. **REG** – Regular file
3. **CHR** – Character special file.
4. **FIFO** – First In First Out

## List User Specific Open Files

The below command will display the list of all opened files of user **cyberpunk**.

![[Pasted image 20230712231257.png]]


## Find Processes running on Specific Port

To find out all the running process of specific port, just use the following command with option **-i**. The below example will list all running process of port **22**.

![[Pasted image 20230712231320.png]]

## List Only IPv4 & IPv6 Open Files

In below example shows only **IPv4** and **IPv6** network files open with separate commands.

![[Pasted image 20230712231351.png]]


## List Open Files of TCP Port ranges 1-1024

To list all the running process of open files of **TCP** Port ranges from **1-1024**.

![[Pasted image 20230712231506.png]]

## Exclude User with ‘^’ Character

Here, we have excluded **root** user. You can exclude a particular user using **‘^’** with command as shown above.

![[Pasted image 20230712231534.png]]

## Find Out who’s Looking What Files and Commands?

Below example shows user **cyberpunk** is using command like **ping** and **/etc** directory.

![[Pasted image 20230712231600.png]]

## List all Network Connections

The following command with option **‘-i’** shows the list of all network connections ‘**LISTENING & ESTABLISHED’**.

![[Pasted image 20230712231627.png]]

## Kill all Activity of Particular User

Sometimes you may have to kill all the processes for a specific user. Below command will kills all the processes of **cyberpunk** user.

![[Pasted image 20230712231652.png]]