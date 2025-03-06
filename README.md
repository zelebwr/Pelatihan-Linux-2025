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

After you have it installed, make a new folder named "artists_who_can_sing" and navigate to it:

```bash
$ mkdir artists_who_can_sing && cd artists_who_can_sing
```

## 2. Inside the "artists_who_can_sing" folder, download the tutorial files
    
Open the google drive link from the [google document](https://drive.google.com/file/d/1lV1HVmPTY_BOAK6ToXymRu7V5eVfR0ut/view?usp=sharing) and then press the download button to get the real zip file download [link](https://drive.usercontent.google.com/u/0/uc?id=1lV1HVmPTY_BOAK6ToXymRu7V5eVfR0ut&export=download). 

After getting the link enter the command line below:
    
```bash
$ wget -O tutorials.zip --no-check-certificate '<link>'
```

Replace the \<link\> with the actual link for the download.

## 3. Unzip the tutorials.zip file into the _new_ singing_tutorials folder

Use the following command to unzip the tutorials.zip file:

```bash
$ unzip tutorials.zip -d singing_tutorials
```

> - The -d flag specifies the destination directory for the files.
> - If the directory "singing_tutorials" doesn't exist, it will be created.

## 4. Navigate to the singing_tutorials folder and list all files and directories, including hidden files

Use the following command to navigate into singing_tutorials and list all files and directories, and then list it again including the hidden files:

```bash 
$ cd singing_tutorials/ && ls && ls -a
```
> - ls is for listing files and directories in the current working directory.
> - Using the -a flag to list all files and directories, including hidden files.

## 5. Find all files with the name "opera" and "NBAYoungboy" in the singing_tutorials folder and extract the FLAG from the file

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

## 6. Go back on directory and then use the link from the flag.txt to download "plsrunmeiamnotmalwarefr" file.

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



chmod +x ./plsrunmeiamnotmalwarefr && ./plsrunmeiamnotmalwarefr

ps aux

touch ransom.moolah && ps aux

kill 1712 && ps aux

sudo adduser yabadabadoo --ingroup sudo && groups yabadabadoo && su - yabadabadoo

mkdir fufufafa && chmod 700 fufufafa && ls -l && cd fufufafa

grep -rhP '^[0-9]{8}: (?!.*0000( 0000){7}$)' /var/tmp/pls_solve_this_puzzle/ | sort -u | grep -oP '(?<=:).*' | tr " \n" " " | sed 's/[ ]\+/ /g' | grep -oP '.*(?=.*0000( 0000){4})' | xxd -r -p > ./flag2.txt

sudo cp /home/zele/college/programming/sms2/sisop/latPrak1/artists_who_can_sing/flag.txt .

sudo rm -rf /var/tmp/pls_solve_this_puzzle/
