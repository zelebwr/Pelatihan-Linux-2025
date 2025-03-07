# Pelatihan-Linux-2025 Command Lines

## 1. wget,  unzip, and xxd

How to check if wget, unzip, and xxd are installed:

```bash
$ wget --version
$
$ xxd --version
$
$ unzip 
```

If you don't have them installed, you can install them using: 

```bash
$ sudo apt install wget unzip xxd
```

After you have it installed, make a new folder named _artists_who_can_sing_ and navigate to it:

```bash
$ mkdir artists_who_can_sing && cd artists_who_can_sing
```

## 2. Inside the _artists_who_can_sing_ folder, download the tutorial files
    
Open the google drive link from the [google document](https://drive.google.com/file/d/1lV1HVmPTY_BOAK6ToXymRu7V5eVfR0ut/view?usp=sharing) and then press the download button to get the real zip file download [link](https://drive.usercontent.google.com/u/0/uc?id=1lV1HVmPTY_BOAK6ToXymRu7V5eVfR0ut&export=download). 

After getting the link enter the command line below:
    
```bash
$ wget -O tutorials.zip --no-check-certificate '<link>'
```

Replace the \<link\> with the actual link for the download.

## 3. Unzip the tutorials.zip file into the new _singing_tutorials_ folder

Use the following command to unzip the tutorials.zip file:

```bash
$ unzip tutorials.zip -d singing_tutorials
```

> - The -d flag specifies the destination directory for the files.
> - If the directory _singing_tutorials_ doesn't exist, it will be created.

## 4. Navigate to the _singing_tutorials_ folder and list all files and directories, including hidden files

Use the following command to navigate into _singing_tutorials_ and list all files and directories, and then list it again including the hidden files:

```bash 
$ cd singing_tutorials/ && ls && ls -a
```
> - ls is for listing files and directories in the current working directory.
> - Using the -a flag to list all files and directories, including hidden files.

## 5. Find all files with the name "opera" and "NBAYoungboy" in the _singing_tutorials_ folder and extract the FLAG from the file

For this, make sure the last output will only show one line of the right file and flag.

Make sure to redirect the output to "flag.txt" file. 

Use the following command to find the correct file: 

```bash 
$ find -name "*opera*NBAYoungboy*" -exec grep -o "FLAG{.*}" {} \; > ../flag.txt
```

> 1. Find with the "-name" flag to find the files with the designated pattern.
>       - The asterisk (*) is a wildcard character that matches any sequence of characters.  
> 2. Use the "-exec" flag to execute a command for each matching file.  
>       - In this case the specific command to add is "grep" to find the FLAG in the file.
>   3. Use the "-o" flag to print only the matched part of the line.  
>       - '.' in RegEx means to match any type of character.  
>       - '*' in RegEx means to match any number of any preceding character.  
>       - '{}' in the command line is used to refer to the output of the find command.  
>       - '\;' at the end of the command line is used to indicate the end of the command from the '-exec' command.
> 4. Redirect the output to the "flag.txt" file.  
>       - The '>' operator redirects (overwrite) the output to a file.    
>       - The '>>' operator appends the output to a file.

## 6. Go back on directory and then use the link from the flag.txt to download _plsrunmeiamnotmalwarefr_ file.

This step can be done easily just by using the wget command. Use the following command:

```bash
$ cd .. && grep -oP "(?<={).*(?=})" flag.txt | wget -O 'plsrunmeiamnotmalwarefr' -i -
```

> 1. Use the 'grep' command to extract the URL from the flag.txt file.  
>       - You can merge two flags together by just jointing them together like '-oP' for combining '-o' and '-P' flag  
>       - The '-P' flag enables Perl-compatible regular expressions (RegEx).  
>       - The regular expression (?<=...) is a positive lookbehind  
>       - The regular expression (?=...) is a positive lookahead  
>       - To do the negative version, just change the '=' in the positive version into
>
> 2. Use the '|' operator to pipe the output of the 'grep' command to the 'wget' command.  
>       - The '-O' flag to specify the output file name.  
>       - The '-i' flag to make 'wget' receive input from a file.  
>       - The '-' flag to indicate where the pipe input will be located at in the wget command.

## 7. Change and check the _plsrunmeiamnotmalwarefr_ file permission

The way you can check the permission for a file is simply by using the list (ls) command.  
Meanwhile you can change the permission by using the change mode (chmod) command.

Use the following command: 

```bash
$ chmod +x ./plsrunmeiamnotmalwarefr && ./plsrunmeiamnotmalwarefr
```

> 1. '+x' flag in chmod is to add "execute" permission to the plsrunmeiamnotmalware file.  
>       - By not adding in what group chmod should add the permission to, it will by default add the permission to the user/owner's permission for the file.
>
> 2. To check the permissions information, we can use the:
>       ```bash
>       $ ls -l
>       ```
>       Where the '-l' flag is for ls command use a long listing format.

## 8. Show the background running process of the _plsrunmeiamnotmalwarefr_

For showing the background running process of the _plsrunmeiamnotmalwarefr_ file, you can imagine it as the same as using the task manager in windows but in terminal.   
You could achieve this by using the following command:

```bash
$ ps aux
```

> 1. 'ps' is short for "process status", where it literally is for showing the process status.
touch ransom.moolah && ps aux
> 2. 'a' argument in the 'ps' command is indicating "all users" process status
> 3. 'u' argument in the 'ps' command is indicating "detailed user information" process status
> 4. 'x' argument in the 'ps' command is indicating "show processes not attached to a terminal" process status,  
So it can show the running processes that's currently running including the background services that's not connected to the terminal

## 9. Create _ransom.moolah_ and check the process status again

We can create files easily by using the 'touch' command. 

Use the following command to do this step:

```bash
$ touch ransom.moolah && ps aux

``` 

## 10. Kill the process from the _plsrunmeiamnotmalwarefr_ file

To achieve this step, you can just use the kill command

```bash
$ kill 1712 && ps aux
```

> '1712' is the Process ID (PID) for the plsrunmeiamnotmalware process.

## 11. Create new user _yabadabadoo_, add it into sudoers group, check the group status of the user, and login to the user

1. To create a new user, we can use the adduser / useradd command.  
     - Where adduser is the high-level version and useradd is the low-level version for "adding a user" command.  
    - "High-level" means it's more user-friendly, "low-level" means it's more technical and have a higher control and higher skill requirements in detailed command executions  
2. To add the user into the group, we can use the usermod (user modification) command or by using the flag in adduser command while creating the user, simultaneously creating and adding the user into a specific group.  
    - In 'usermod' we can use the -aG flag to "append" to what "Group" 
    - In 'adduser' we can use the '--ingroup' flag to "add" to what "Group" while simultaneously creating the new user
3. To check whether the user has already gotten into the right group, we can use the 'groups' command 
4. To login into the user we can use the 'su' (switch user) command
    - There are multiple ways to use the 'su' command. One is with the format:  

        ```bash
        $ su <username>
        ```
        Where it switches the user without changing the shell environment.  

        And the other one is:

        ```bash
        $ su - <username>
        ```

        Where it switches the user while also changing the shell environment. This will act like a new login session for the user, providing better security and environment isolation

You could use the following command:

```bash
$ sudo adduser yabadabadoo --ingroup sudo && groups yabadabadoo && su - yabadabadoo
```

## 12. Create new folder/directory _fufufafa_ and change the permission so that the only the owner and root can access it

To do this step, we can use the 'mkdir' (make directory) command to create the new directory and then the chmod (chmod) to change the permission.

You could see the following command:

```bash
$ mkdir fufufafa && chmod 700 fufufafa && ls -l && cd fufufafa
```

> 1. 'mkdir' to create new directory called "fufufafa"
> 2. 'chmod' to change the directory permissions
>       - The numbers is for easily setting permissions in each owner/group/others permissions
>          - The value 4 for the permission "read" 
>          - The value 2 for the permission "write"
>          - The value 1 for the permission "execute"
>       - The number position syntax is "ugo"  
>           - u = user/owner  
>           - g = group  
>           - o = others
>
>           And since '7' is "4+2+1" it will represent "r+w+x" according to the respective values. This "addition" concept goes with how to add the permissions of ugo using numbers  
>       - So '700' means owner will have rwx permission and group and others have no permissions

## 13. Get the second flag in _pls_solve_this_puzzle_ in /var/tmp and put it in the _fufufafa_ directory

If you check on the _/var/tmp/pls_solve_this_puzzle_ directory, you will find the "pls_solve_this_puzzle" directory which contains a lot of _.html_ files and directories that contains more _.html_ files and subdirectories that contains even more _.html_ files.

If you check the inside of _.html_ files, you can see that there's a lot of lines that is filled with a lot of random sequence of characters as a string. 

There are some that contains a random sequence of characters, and some that contains a sequence of some sort of hexadecimal characters.

Since in the puzzle, there's a hint about the second flag being a string of hexadecimal characters, the base assumption is that the second flag is in the files that contains a string of hexadecimal characters.

You could use the following command to get the second flag: 

```bash
$ grep -rhP '((?<=([0-9]{8}: )))(?!0000( 0000)pls_solve_this_puzzle/ | grep -oP '(?<=: ).*' | tr "\n" " " | grep -oP '.*(?=.*0000( 0000){4})' | xxd -r -p
```
As you can see, that command is absolutely absurd.

> 1. The first 'grep' here is used to search some sort of text inside the files.  
>       - The '-r' flag is to search recursively in all files and subdirectories in the specified directory
>       - The '-h' flag is to suppress prefixing the filenames containing the matched condition. So, it only outputs the matching lines instead of returning the filenames as well
>       - The '-P' flag is to interpret the pattern as a Perl regular expression
>       - The '^[0-9]{8}:' pattern is looking for lines that starts with a sequence of exactly 8 characters of any of the numbers (0-9) followed by a colon.  
>           - Since in all of the files when you try searching with '^[0-9a-zA-z]{8}:' pattern, you could see that the lines with the hexadecimal characters starts with only '^[0-9]{8}:' pattern
>       - The '(?!.*0000( 0000){7}$)' at the end of the pattern is a negative lookahead assertion. It means that it will only match lines that does not contain the pattern. 
>           - In this case, it will only match lines that does not contain exactly 7 consecutive '0000'
>       - The '/var/tmp/pls_solve_this_puzzle/' means in what directory the grep should search at
> 
> 2. The 'sort' here is used to sort the output lines  
>       - The '-u' flag stands for "--unique", meaning it will only match with the first occurrence of input. This will remove any duplicates from the input.
>
> 3. The "grep -oP '(?<=:).*'" here is used to extract the characters after the colon from each line  
>       - The '(?<=:)' is a positive lookbehind assertion. It means that it will only match the characters after the colon.
>       - The '.*' is a wildcard that matches any character (except newline) zero or more times.
>
> 4. The 'tr' command i short for "translate". Here it is used to replace all newline characters (\n) with a space in the output. This will merge multiple lines into a single line
> 
> 5. The 'sed' command is short for "stream editor". Here it is used to replace all spaces with a single space in the output. This will remove any extra spaces from the output
> 
>       - The 's/[ ]\+/ /g' here mean to change multiple occurrences of spaces with a single space by using the RegEx pattern.
> 6. The "grep -oP '.*(?=.*0000( 0000){4})'" here is used to extract the characters before the sequence of exactly 5 consecutive '0000' separated with a space from each line
>
> 7. The 'xxd -r -p' here is used to convert the hexadecimal characters back to the original string. 
>       - The '-r' flag stands for "revert", meaning it will convert the hexadecimal characters to the original string in reverse order
>      - The '-p' flag will print the output in a format that can easily be read
>
> 8. The '> ./flag2.txt' is to redirect the output to a file named "flag2.txt" in the current directory.

## 14. Copy the flag.txt file from before to the current directory

Doing this is simply enough use the 'cp' command, like following: 

```bash
$ sudo cp /home/zele/college/programming/sms2/sisop/latPrak1/artists_who_can_sing/flag.txt .
```

## 15. Remove the _/var/tmp/pls_solve_this_puzzle_ directory

This can be done by using the 'rm' command with the '-rf' flag, which stands for "recursive forcefully". This will remove the directory and all its contents. Use the following command:

```bash
$ sudo rm -rf /var/tmp/pls_solve_this_puzzle/
```
