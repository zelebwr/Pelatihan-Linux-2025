# Pelatihan-Linux-2025 Command Lines

## 1. wget,  unzip, and xxd

How to check if wget, unzip, and xxd are installed:

```bash
$ wget --version
$ xxd --version
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
$wget -O tutorials.zip --no-check-certificate '<link>'
```

Replace the \<link\> with the actual link for the download.

## 3. Unzip the tutorials.zip file into the _new_ singing_tutorials folder

Use the following command to unzip the tutorials.zip file:

```bash
unzip tutorials.zip -d singing_tutorials
```

> The -d flag specifies the destination directory for the files.
>
> If the directory "singing_tutorials" doesn't exist, it will be created.

## 4. Navigate to the singing_tutorials folder and list all files and directories, including hidden files

Use the following command to navigate into singing_tutorials and list all files and directories, and then list it again including the hidden files:

```bash 
cd singing_tutorials/ && ls && ls -a
```
> ls is for listing files and directories in the current working directory.
>
> Using the -a flag to list all files and directories, including hidden files.

## 5. 
find -name "*opera*NBAYoungboy*" -exec grep -o "FLAG{.*}" {} \; > ../flag.txt

cd .. && grep -oP "(?<={).*(?=})" flag.txt | wget -O 'plsrunmeiamnotmalwarefr' -i -

chmod +x ./plsrunmeiamnotmalwarefr && ./plsrunmeiamnotmalwarefr

ps aux

touch ransom.moolah && ps aux

kill 1712 && ps aux

sudo adduser yabadabadoo --ingroup sudo && groups yabadabadoo && su - yabadabadoo

mkdir fufufafa && chmod 700 fufufafa && ls -l && cd fufufafa

grep -rhP '^[0-9]{8}: (?!.*0000( 0000){7}$)' /var/tmp/pls_solve_this_puzzle/ | sort -u | grep -oP '(?<=:).*' | tr " \n" " " | sed 's/[ ]\+/ /g' | grep -oP '.*(?=.*0000( 0000){4})' | xxd -r -p > ./flag2.txt

sudo cp /home/zele/college/programming/sms2/sisop/latPrak1/artists_who_can_sing/flag.txt .

sudo rm -rf /var/tmp/pls_solve_this_puzzle/
