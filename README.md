# :shipit: OverTheWire: Bandit, Level 0-15 Write-up

![image](https://user-images.githubusercontent.com/84661482/132093151-7b225882-2b7c-4973-8150-4df05617ea59.png)

## :clipboard: Table of Contents

- [:open_book: Introduction](#open_book-introduction)
- [:triangular_flag_on_post: Bandit Level 00](#triangular_flag_on_post-bandit-level-0)
- [:triangular_flag_on_post: Bandit Level 00 - 01](#triangular_flag_on_post-bandit-level-00---01)
- [:triangular_flag_on_post: Bandit Level 01 - 02](#triangular_flag_on_post-bandit-level-01---02)
- [:triangular_flag_on_post: Bandit Level 02 - 03](#triangular_flag_on_post-bandit-level-02---03)
- [:triangular_flag_on_post: Bandit Level 03 - 04](#triangular_flag_on_post-bandit-level-03---04)
- [:triangular_flag_on_post: Bandit Level 04 - 05](#triangular_flag_on_post-bandit-level-04---05)
- [:triangular_flag_on_post: Bandit Level 05 - 06](#triangular_flag_on_post-bandit-level-05---06)
- [:triangular_flag_on_post: Bandit Level 06 - 07](#triangular_flag_on_post-bandit-level-06---07)
- [:triangular_flag_on_post: Bandit Level 07 - 08](#triangular_flag_on_post-bandit-level-07---08)
- [:triangular_flag_on_post: Bandit Level 08 - 09](#triangular_flag_on_post-bandit-level-08---09)
- [:triangular_flag_on_post: Bandit Level 09 - 10](#triangular_flag_on_post-bandit-level-09---10)
- [:triangular_flag_on_post: Bandit Level 10 - 11](#triangular_flag_on_post-bandit-level-10---11)
- [:triangular_flag_on_post: Bandit Level 11 - 12](#triangular_flag_on_post-bandit-level-11---12)
- [:triangular_flag_on_post: Bandit Level 12 - 13](#triangular_flag_on_post-bandit-level-12---13)
- [:triangular_flag_on_post: Bandit Level 13 - 14](#triangular_flag_on_post-bandit-level-13---14)
- [:triangular_flag_on_post: Bandit Level 14 - 15](#triangular_flag_on_post-bandit-level-14---15)

## :open_book: Introduction

OverTheWire is a community that can help you to learn and practice security concepts in the form of fun-filled games. They offer lots of wargames to practice your skills.

![image](https://user-images.githubusercontent.com/84661482/132092828-c917b13e-0df0-4052-b7a7-a7a9d7162d8f.png)

The first set of challenges is named "Bandit," and it's more of a tutorial to the Linux CLI, with each level's goal being to discover the password to move to the next. 

![image](https://user-images.githubusercontent.com/84661482/132092898-322b815b-674e-4dd7-a457-e824d910ae43.png)

The follwing content is a comprehensive write-up of my solutions for this challenge (Level 0 - 15). Before looking at the answers, I recommend doing it yourself because you won't learn anything unless you try. My primary idea is to demonstrate you how I handled it and to compare your solutions to mine. 


## :triangular_flag_on_post: Bandit Level 00

### Problem Description:
Level 0 is a welcome gift to get you started with the real difficulties. 

![image](https://user-images.githubusercontent.com/84661482/132093444-428e2ad1-dba7-44ac-be13-ae2561b4ee94.png)

### Solution & Explanation:
To begin, you must understand how to use the secure shell (SSH) protocol to connect to the bandit.labs.overthewire.org server. If you're using Linux, you may access the server by running the following command: 

```
sasha@SecurityBox:~$ ssh bandit.labs.overthewire.org -l bandit0 -p 2220
```
If you're using Windows, though, you won't find an SSH client by default. While there are several great SSH clients available for use in Windows environments, I like PuTTY since it is straightforward and relatively compact. 

![image](https://user-images.githubusercontent.com/84661482/132094175-36de91a1-df1b-413f-af47-54a7e660dcc5.png)

When you're finished, hit "Open," and you'll be able to access the bandit0 shell. 

![image](https://user-images.githubusercontent.com/84661482/132094368-4fb40674-9827-4514-ad0c-2d2dabbb62c6.png)

## :triangular_flag_on_post: Bandit Level 00 - 01

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132094626-39a1e512-5658-4feb-bd4f-187f34b17514.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132095287-b57a70c6-9da9-49d7-b866-5fdc4bb5535c.png)

### Explanation:
This level is also a straightforward giveaway. As suggested by the level's hint, run **ls** to examine the current directory, then **cat** the **readme** file to view its information. 

If you don't understand the meaning behind any of these commands. Well, try to read the manual pages! **man** is the name of the command that pulls up manpages. So you use **man** by doing this:

```
$ man [name of program you are interested in]
```
Here is the manpages of **ls** and **cat**:

![image](https://user-images.githubusercontent.com/84661482/132094920-0aff3cb2-39e4-4e06-8574-6f2fc68ceef1.png)
![image](https://user-images.githubusercontent.com/84661482/132094944-74dbbc26-2820-4743-8860-a39e2ac2a0c6.png)

### Summary:
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
 ```
The password to the level 01's box is **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**


## :triangular_flag_on_post: Bandit Level 01 - 02

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132095632-36c26f4f-fb81-4d88-b24e-a99d61969ad7.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132095451-5e70e4bb-ee33-4120-b751-61495d4f9a88.png)

### Explanation:
To acquire the password for stage 2, we have to print the content of the file called **–** (the dash symbol), as recommended by the hint.

If you just use the **cat** command to read and print the contents of the file called **–**, unfortunately, your terminal will become stuck. 

![image](https://user-images.githubusercontent.com/84661482/132095836-3a04ea80-ed4a-4e20-b2b6-a7a0bd326dc3.png)

When **cat** encounters the filename **–**, it interprets it as a synonym for **STDIN**. You must supply the full path of the file rather than just the file name to avoid being regarded as an **STDIN** and your terminal getting nothing. 

### Summary:
```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
The password to gain access to the level 02's box is **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**


## :triangular_flag_on_post: Bandit Level 02 - 03

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132096087-ff16cc31-aa39-4460-8923-a2ef74034e4f.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132096150-93de2a1d-86a4-44c0-949c-fb5989953c43.png)

### Explanation:
You'll see the "spaces in this filename" file after running a **ls** command to examine the files in the directory. You will encounter issues if you **cat** the file directly.

Either use a backslash before each space or write the full file name as a string. As an example: 
1. Adding backslash before each space:    
```
bandit2@bandit:~$ cat spaces\ in\ this\ filename
```
2. Adding double quote:
```
bandit2@bandit:~$ cat "spaces in this filename"
```
When can also use **tab completion** by pressing **tab**, which makes the program automatically fills in partially typed commands. 

### Summary:
```
bandit2@bandit:~$ ls 
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
The password to gain access to the level 03's box is **UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK**


## :triangular_flag_on_post: Bandit Level 03 - 04

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132096510-977f84a2-01ec-4a5c-b212-ca68d47fb5b8.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132096604-c0ef8903-b5a0-40e7-bac3-48e62c6d5184.png)

### Explanation:
Because the file is hidden, just use **ls -a** to find it. To learn about how flags such as **-a** or **-l** work, you can use **man ls**.

![image](https://user-images.githubusercontent.com/84661482/132096705-30315891-0053-4728-9e45-ac203ebbf252.png)

### Summary:
```
bandit3@bandit:~/inhere$ ls -al
total 12
drwxr-xr-x 2 root    root    4096 May  7  2020 .
drwxr-xr-x 3 root    root    4096 May  7  2020 ..
-rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
The password to gain access to the box in level 04 is **pIwrPrtPN36QITSp3EQaw936yaFoFgAB**


## :triangular_flag_on_post: Bandit Level 04 - 05

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132097153-678cb54e-cdff-4439-98b6-2b9b44ae25ec.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132097269-e13cfd45-fc9c-48ca-8e0b-7c327f964b3a.png)

### Explanation:
Because just one file is human-readable and contains the password for the following round, rather than accessing each file one by one and reading its content, we may print all of each text and spot the password using: 
```
bandit4@bandit:~/inhere$ cat ./-file0*
```
The asterisk ( * ) is a wildcard that represents any number of unknown characters. This is useful when searching for documents or files but only remembering a part of its name. Here's what we got from using the command above:
```
�/`2ғ�%��rL~5�g��� �������p,k�;��r*��	�.!��C��J	�dx,�e�)�#��5��
                                                                       ��p��V�_���ׯ�mm������h!TQO�`�4"aל�߂phT��,�?��r�l$�?h�9('���!y�e�#�x�O��=��ly���~��A�f����-E�{���m�����ܗkoReBOKuIDDepwhWk7jZC0RTdopnAYKh
�T�?�i��j��îP�F�l�n��J����{��@�e�0$�in=��_b�5FA�P7sz��gN
```
As you can see, the only human-readable string is **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**. 

However, if you want to know which file is containing the password, you may use my preferred method for this problem. Execute the following command: 
```
bandit4@bandit:~/inhere$ find . -type f | xargs file
```
We're basically using **find** (read the manpages if you don't understand the command) to get the **full paths** of all files in the current directory, and then passing those paths as **STDIN** to the **file** command, which will return the file type. The **xargs** command is used to perform the **file** command for each line. 

![image](https://user-images.githubusercontent.com/84661482/132116626-c0aa8f21-fde9-4f50-9e29-428a36df7778.png)
![image](https://user-images.githubusercontent.com/84661482/132116639-fae16bee-61e7-4381-a41a-9af9e3906fb9.png)
![image](https://user-images.githubusercontent.com/84661482/132120514-21d14d1f-fc56-4615-a63b-fb11b56af97d.png)

We'll know the human-readable file is "./-file07" this way, and then we're going to be able to **cat** the password directly from it.


### Summary:
```
bandit4@bandit:~/inhere$ ls -l
total 40
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file00
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file01
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file02
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file03
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file04
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file05
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file06
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file07
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file08
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file09
bandit4@bandit:~/inhere$ find . -type f | xargs file
./-file01: data
./-file00: data
./-file06: data
./-file03: data
./-file05: data
./-file08: data
./-file04: data
./-file07: ASCII text
./-file02: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```
The password to gain access to the level 05's box is **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**


## :triangular_flag_on_post: Bandit Level 05 - 06

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132098234-70625080-89d7-4ce1-b42a-f678c419f762.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132099309-e68ea946-a05c-4754-993e-bf35e4e4f116.png)

### Explanation:
The first thing we do when we start a new level is to run the **ls** command to see what files we have access to, just as we do with any other level. And wow, we're looking at 80 files in this instance. 
```
total 80
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere00
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere01
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere02
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere03
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere04
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere05
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere06
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere07
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere08
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere09
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere10
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere11
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere12
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere13
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere14
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere15
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere16
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere17
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere18
drwxr-x--- 2 root bandit5 4096 May  7  2020 maybehere19
```
Well, 80 files is much too plentiful for manual inspection; imagine running cat on each and every one of them; it is not only absurd, but also impractical – what if there were 8000 files instead of 80? 

We must use the suggestions provided to limit down the scope, for example, a file that is human-readable and 1033 bytes in size. In this case, the **find** command makes life a lot easier; read the manpage and look for an appropriate flag that will help you search for files that match your criteria. We may utilize the **type** and **size** parameters in this case: 

![image](https://user-images.githubusercontent.com/84661482/132099521-f59c8c0a-271c-41c8-9b3a-703f95a370bd.png)
![image](https://user-images.githubusercontent.com/84661482/132099495-c17a33f1-a6de-46f1-8455-ad72485e7115.png)

### Summary:
```
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
The password to gain access to the level 06's box is **DXjZPULLxYr17uwoI01bNLQbtFemEgo7**


## :triangular_flag_on_post: Bandit Level 06 - 07

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132099614-4a865824-77e7-4981-b764-42aa64509734.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132120379-0946d7c6-2d31-4299-bbbb-24073b5263f3.png)

### Explanation:
This level is quite similar to the previous one, which you should have completed using the **find** command by now. However, because the scope of the search includes the entire drive of the computer rather than just 80 files in a folder, we need to provide extra parameters to be more particular in what we want to look for at this level. 
```
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -type f -size 33c
/var/lib/dpkg/info/bandit7.password
```
The above command searches from the **root** directory (the first or top-most directory in the Linux Filesystem Hierarchy Standard), as shown by **the slash (/)** sign right after the **find** command. Other parameters include: 

1. **user**, which defines the file owner, bandit7
![image](https://user-images.githubusercontent.com/84661482/132120605-2a76f621-7e7c-40ce-ae03-b857b2873454.png)

2. **group**, which defines the file group, bandit6 in this case
![image](https://user-images.githubusercontent.com/84661482/132100463-ee3b00a3-1675-4022-ae14-221ba177ed66.png)

3. **size**, which defines the size of the file. 33c means 33 bytes of characters

### Summary:
```
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
The password to gain access to the level 07's box is **HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs**


## :triangular_flag_on_post: Bandit Level 07 - 08

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132100649-9af7bc21-70a6-40e6-9a72-80ef95cca6fd.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132101128-488b6f7c-25f2-4d0d-a61e-fa7d307bafa0.png)

### Explanation:
This level is really rather straightforward and can be completed in a variety of ways, but if you try to get the password by just **cat**-ing the file without doing anything else, you'll quickly regret it since the file includes an endless number of unique strings, making your terminal scroll forever: 

![image](https://user-images.githubusercontent.com/84661482/132101358-9b495607-d703-4b53-8aff-46976a348d72.png)

To stop the terminal from reading the file, press **Ctrl + C**. This powerful command could be able to kill almost every running process in Linux.

So how to solve this level? Personally, I would prefer to simply **cat** the file and then **grep** the keyword mentioned in the hint, “millionth“.

### Summary:
```
bandit7@bandit:~$ cat data.txt | grep 'millionth'
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
The password to gain access to the level 08's box is **cvX2JJa4CFALtqS87jk27qwqGhBM9plV**


## :triangular_flag_on_post: Bandit Level 08 - 09

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132112273-928c1927-dce0-4fc5-92b7-3a5f6767828d.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132112328-2a64245e-3cfb-4c03-bf07-dc5071ec351b.png)

### Explanation:
If you don't understand how commands like **sort** and **uniq** operate, this level may be extremely difficult.

Several commands appear to be capable of generating the result but fail to do so. Personally, I've learned a lot from these mistakes.

Let's have a look at how the **uniq -u** command works first:

![image](https://user-images.githubusercontent.com/84661482/132112413-4e21d4b5-60ab-4bfc-aad8-12421bd5e934.png)

As you can see from the example above, the **uniq -u** command eliminates all instances of consecutively duplicated lines, leaving just the lines that have never been duplicated. What about non-consecutively repeated lines? How may they be arranged adjacent to one other? Well, **sort** will assist you in completing the task:

![image](https://user-images.githubusercontent.com/84661482/132120647-47f5095e-ca1e-4ff1-9274-9b00e86eda3b.png)

In short, we can simply retrieve the unique password line by using the piping technique **|** to combine **sort** and **uniq -u**. 

### Summary:
```
bandit8@bandit:~$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
The password to gain access to the level 09's box is **UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR**

## :triangular_flag_on_post: Bandit Level 09 - 10

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132112961-98c1f971-7a6c-4462-b983-a0f6e1738581.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132113009-97f996a4-759e-46a6-85db-58bb2cb3d18a.png)

### Explanation:
As with previous stages, we must search for the password within a text file. But you can't use the **cat** and **grep** commands since it's a "binary" file instead of a text file, which makes this level tough. 
```
bandit9@bandit:~$ cat data.txt | grep "="
Binary file (standard input) matches
```
Try the **strings** command at this point. If you want to know more about what **strings** command does, read its manpage:

![image](https://user-images.githubusercontent.com/84661482/132120684-0f66782c-fded-4cd6-9c2e-ac892954e474.png)

In other words, it searches the whole file for any string values it can examine and displays them in the output.
Now let us run a strings command on the **data.txt** file and **grep** only records containing the “=” characters, as per the hint given to us to pass this level. 

### Summary:
```
bandit9@bandit:~$ strings data.txt | grep "="
========== the*2i"4
=:G e
========== password
<I=zsGi
Z)========== is
A=|t&E
Zdb=
c^ LAh=3G
*SF=s
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
S=A.H&^
bandit9@bandit:~$ 
```
The password to gain access to the level 10's box is **truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk**

## :triangular_flag_on_post: Bandit Level 10 - 11

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132113199-b115a966-6ad1-490a-8eb1-1e3428477b46.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132113520-97f6b630-35a3-4089-82bb-cb016f8974ae.png)

### Explanation:
This level primarily introduces us to **base64** encoding, which is one of the most widely used methods for encoding data in the wild. However, owing to the abundance of tools accessible online, it is simple to detect and decode. 

![image](https://user-images.githubusercontent.com/84661482/132113585-80de6573-e981-41d1-9e48-76a0100f5b58.png)
 
However, we can easily do a **base64** decode because the server is running on a Linux distribution and all Unix operating systems have built-in support for the **base64** command. 

### Summary:
```
bandit10@bandit:~$ base64 -d data.txt 
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

```
The password to the level 11's box is **IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR**

## :triangular_flag_on_post: Bandit Level 11 - 12

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132113678-40623a30-698b-406e-9e1b-e452fc9ff164.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132120722-93cb175e-01f8-40f6-8456-4b6586f1e525.png)

### Explanation:
As provided in the hint, we are required to perform a ROT13 “decode” on the file given. First, let’s look at the clue,
```
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh
```
Now, we can decode this using any decoding tool that you like. I myself use [CyberChef](https://gchq.github.io/CyberChef/)

![image](https://user-images.githubusercontent.com/84661482/132115018-89618cea-035d-4ec8-896c-949ac7bbfd8f.png)

However, if you believe solving this problem using a built-in Linux command is sexier, there is a method to imitate the **ROT13** decoding process with the **tr** command: 

![image](https://user-images.githubusercontent.com/84661482/132120444-afb2d776-a0a1-4f79-b9bf-612134ffeb2f.png)

![image](https://user-images.githubusercontent.com/84661482/132115119-3a0c3a7b-9b80-480b-9ebb-cff557175410.png)

For this problem, **tr** command is used to translate the first set of characters ‘A-Za-z’ to ‘N-ZA-Mn-za-m’ which is a rotation of 13 positions of the first set.

### Summary:
```
bandit11@bandit:~$ cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```
The password to the level 12's box is **5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu**

## :triangular_flag_on_post: Bandit Level 12 - 13

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132115221-1c931f51-d300-4d82-912c-ae8fe3233387.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132115537-f098e5d2-36d3-4868-b1e5-977569db155a.png)

### Explanation:
This is one of the most difficult levels in the CTF challenge. Let's start by moving the file to a new directory under your name in the **/tmp** folder (make one with the **mkdir** command!). 
```
bandit12@bandit:~$ mkdir /tmp/sasha/
```
Copy the data.txt file from **~** to **/tmp/yourusername/**:
```
bandit12@bandit:~$ cp data.txt /tmp/sasha/data.txt
```
Change the working directory to **/tmp/yourusername** using cd:
```
bandit12@bandit:~$ cd /tmp/sasha/
```
Let's see what's in the file using **cat**:
![image](https://user-images.githubusercontent.com/84661482/132116371-ae5b9361-26c7-415d-b85b-b2da00ed0a7c.png)

As you can see, this is a hexdump, which was converted by the **xxd** command. 

![image](https://user-images.githubusercontent.com/84661482/132116608-6cbceb9d-8b04-4df6-9224-8f04cbc1c704.png)

**xxd** is not really a hex-editor, it just displays hex. However, we can use it to convert files into hex, make edits to them with our favorite text editors, then convert the files back into the correct formats.

Anyway, now we have to perform a reverse hashdump using **xxd** command:

```
bandit12@bandit:/tmp/sasha$ xxd -r data.txt > password
```
After running the reverse hexdump command and saving the result to a file (I named mine "password"), use the **file** command to see what type of file it is.
```
bandit12@bandit:/tmp/sasha$ file password 
password: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
```
From here on onwards, the flow is as follows:

1. Using the file command, determine what format of file this is.
2. Using the mv command to alter the file type by renaming it to that specific file format extension.
3. Using the appropriate tool to decompress/unzip the files (in this case, **gzip** or **gunzip**, **bzip2** and **tar** play a significant role).
4. Repeat steps 1-3 until you get the file.

The list of commands I have is as below; it will be pretty long. It does, however, follow the process that I outlined before. To make things simpler to understand, I've included a "line break" after each change in file type. I hope it proves useful! 

### Summary:
```
bandit12@bandit:/tmp/sasha$ xxd -r data.txt > password

bandit12@bandit:/tmp/sasha$ file password 
password: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/sasha$ mv password password.gz
bandit12@bandit:/tmp/sasha$ gunzip password.gz 

bandit12@bandit:/tmp/sasha$ file password 
password: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/sasha$ mv password password.bz2
bandit12@bandit:/tmp/sasha$ bzip2 -d password.bz2 

bandit12@bandit:/tmp/sasha$ file password 
password: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/sasha$ mv password password.gz
bandit12@bandit:/tmp/sasha$ gunzip password.gz 

bandit12@bandit:/tmp/sasha$ file password 
password: POSIX tar archive (GNU)
bandit12@bandit:/tmp/sasha$ mv password password.tar
bandit12@bandit:/tmp/sasha$ tar xvf password.tar data5.bin
data5.bin

bandit12@bandit:/tmp/sasha$ file data5.bin 
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/sasha$ mv data5.bin data5.tar
bandit12@bandit:/tmp/sasha$ tar xvf data5.tar data6.bin 
data6.bin

bandit12@bandit:/tmp/sasha$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/sasha$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/sasha$ bzip2 -d data6.bz2 

bandit12@bandit:/tmp/sasha$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/sasha$ mv data6 data6.tar
bandit12@bandit:/tmp/sasha$ tar xvf data6.tar data8.bin
data8.bin

bandit12@bandit:/tmp/sasha$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/sasha$ mv data8.bin data8.gz
bandit12@bandit:/tmp/sasha$ gzip -d data8.gz 

bandit12@bandit:/tmp/sasha$ file data8 
data8: ASCII text

bandit12@bandit:/tmp/sasha$ cat data8
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```
The password to the level 13's box is **8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL**

## :triangular_flag_on_post: Bandit Level 13 - 14

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132117357-5d094efa-5a93-4c48-b90b-ebcdf91c2ffd.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132117470-c6a41fbb-ccfa-47d7-8ad5-4bdf233c31a7.png)
![image](https://user-images.githubusercontent.com/84661482/132117498-762c0519-2c62-4323-bf25-eccd543a6f68.png)

### Explanation:
This level assesses our ability to navigate around numerous servers using the SSH protocol - including logging in without a password. Many businesses prefer this technique of accessing their servers since it protects them against brute-force password cracking. Let's have a look at what's in the **sshkey.private** file that you were given in the **~** directory: 
```
bandit13@bandit:~$ cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
jiPyTF0is8uzMlYQ4l1Lzh/8/MpvhCQF8r22dwIDAQABAoIBAQC6dWBjhyEOzjeA
J3j/RWmap9M5zfJ/wb2bfidNpwbB8rsJ4sZIDZQ7XuIh4LfygoAQSS+bBw3RXvzE
pvJt3SmU8hIDuLsCjL1VnBY5pY7Bju8g8aR/3FyjyNAqx/TLfzlLYfOu7i9Jet67
xAh0tONG/u8FB5I3LAI2Vp6OviwvdWeC4nOxCthldpuPKNLA8rmMMVRTKQ+7T2VS
nXmwYckKUcUgzoVSpiNZaS0zUDypdpy2+tRH3MQa5kqN1YKjvF8RC47woOYCktsD
o3FFpGNFec9Taa3Msy+DfQQhHKZFKIL3bJDONtmrVvtYK40/yeU4aZ/HA2DQzwhe
ol1AfiEhAoGBAOnVjosBkm7sblK+n4IEwPxs8sOmhPnTDUy5WGrpSCrXOmsVIBUf
laL3ZGLx3xCIwtCnEucB9DvN2HZkupc/h6hTKUYLqXuyLD8njTrbRhLgbC9QrKrS
M1F2fSTxVqPtZDlDMwjNR04xHA/fKh8bXXyTMqOHNJTHHNhbh3McdURjAoGBANkU
1hqfnw7+aXncJ9bjysr1ZWbqOE5Nd8AFgfwaKuGTTVX2NsUQnCMWdOp+wFak40JH
PKWkJNdBG+ex0H9JNQsTK3X5PBMAS8AfX0GrKeuwKWA6erytVTqjOfLYcdp5+z9s
8DtVCxDuVsM+i4X8UqIGOlvGbtKEVokHPFXP1q/dAoGAcHg5YX7WEehCgCYTzpO+
xysX8ScM2qS6xuZ3MqUWAxUWkh7NGZvhe0sGy9iOdANzwKw7mUUFViaCMR/t54W1
GC83sOs3D7n5Mj8x3NdO8xFit7dT9a245TvaoYQ7KgmqpSg/ScKCw4c3eiLava+J
3btnJeSIU+8ZXq9XjPRpKwUCgYA7z6LiOQKxNeXH3qHXcnHok855maUj5fJNpPbY
iDkyZ8ySF8GlcFsky8Yw6fWCqfG3zDrohJ5l9JmEsBh7SadkwsZhvecQcS9t4vby
9/8X4jS0P8ibfcKS4nBP+dT81kkkg5Z5MohXBORA7VWx+ACohcDEkprsQ+w32xeD
qT1EvQKBgQDKm8ws2ByvSUVs9GjTilCajFqLJ0eVYzRPaY6f++Gv/UVfAPV4c+S0
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----
```
How can we make use of it? Let's check out the manpage of **ssh**:

![image](https://user-images.githubusercontent.com/84661482/132117893-7e8d4ed8-e048-45d0-a23c-f0bd3bb3ff20.png)

And yes, by using:
```
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost 
bandit14@bandit:~$ 
```
Boom! You've already entered the box for level 14! The password may then be read from the **/etc/bandit pass/bandit14** directory if you want to know it. All level passwords are kept in that directory, as indicated on the level 0 introduction page, however they can only be viewed by the level's user. 

### Summary:
```
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost 

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```
The password to the level 14's box is **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**

## :triangular_flag_on_post: Bandit Level 14 - 15

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132118303-e0680045-9bc6-4bdd-a1eb-48043113e094.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132118394-21dec1e5-450e-4018-93f9-145b1ae9ff55.png)

### Explanation:
As mentioned in the level 0 introduction page, all level’s passwords are stored in **/etc/bandit_pass/** but they can only be accessed by the level’s user.

![image](https://user-images.githubusercontent.com/84661482/132118495-4e7ff567-5009-41e0-bac0-e63108de0dae.png)

Now that we are logged in to bandit14, we can retrieve its password, which is **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**, as I have done in the previous level. So, we need to submit it to port 30000 on localhost. We can do it using many ways, one of them is **echo** and **netcat**.

![image](https://user-images.githubusercontent.com/84661482/132120319-fd77e5d9-2652-42da-ad3e-8c8b0e298a5c.png)
![image](https://user-images.githubusercontent.com/84661482/132118591-6f8cdc1a-2dde-4656-9e3f-940200e8741b.png)

Using pipes and redirectors, we can choose the input that is sent via the network, as well as what we do with the data once we receive them. On the command line we can use **nc** as a short name for the **netcat** program.
```
bandit14@bandit:~$ echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000
```
When we run this command, we take the **STDOUT** of echo and pipe it as the **STDIN** of netcat. The first argument for **netcat** is the **IP address** we want to send it to (which in this case, is **localhost** or **127.0.0.1**), and the second number is the **port** we want to send it to. **Netcat** will then send the password off to the correct location. 

Another option is to use **telnet**; nevertheless, any method will suffice. There are several additional options, but we won't get into them now. 
```
bandit14@bandit:~$ telnet localhost 30000
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr

Connection closed by foreign host.
```

### Summary:
```
bandit14@bandit:~$ echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```
The password to the level 15's box is **BfMYroe26WYalil77FoDi9qh59eK5xNr**

## Acknowledgement:
Inspiration and Motivation have always played a key role in the success of any individual. 

I express my sincere thanks to [Mr. Dennis Devey](https://twitter.com/deveynull) and his community on Slack for setting up the assignment in his [course](https://roppers.thinkific.com/courses/computing-fundamentals), which gives me a chance to get used to writing CTF writeups. This experience will definitely play an important role in my learning journey.

Sep, 5th 2021,

Cuong Nguyen






