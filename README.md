# :shipit: OverTheWire: Bandit, Level 0-15 Writeup

<p align="center">
  <img width="833" height="455" src="https://user-images.githubusercontent.com/84661482/132093151-7b225882-2b7c-4973-8150-4df05617ea59.png">
</p>

## Table of Contents


## :open_book: Introduction

OverTheWire is a community that can help you to learn and practice security concepts in the form of fun-filled games. They offer lots of wargames to practice your skills.

![image](https://user-images.githubusercontent.com/84661482/132092828-c917b13e-0df0-4052-b7a7-a7a9d7162d8f.png)

The first set of challenges is named "Bandit," and it's more of a tutorial to the Linux CLI, with each level's goal being to discover the password to move to the next. 

![image](https://user-images.githubusercontent.com/84661482/132092898-322b815b-674e-4dd7-a457-e824d910ae43.png)

The follwing content is a comprehensive write-up of my solutions for this challenge (Level 0 - 15). Before looking at the answers, I recommend doing it yourself because you won't learn anything unless you try. My primary idea is to demonstrate you how I handled it and to compare your solutions to mine. 

## :triangular_flag_on_post: Bandit Level 0

### Problem Description:
Level 0 is a welcome gift to get you started with the real difficulties. 

![image](https://user-images.githubusercontent.com/84661482/132093444-428e2ad1-dba7-44ac-be13-ae2561b4ee94.png)

### Solution & Explanation:
To begin, you must understand how to use the secure shell (SSH) protocol to connect to the bandit.labs.overthewire.org server. If you're using Linux, you may access the server by running the following command: 

```
sasha@SecurityBox:~$ ssh bandit.labs.overthewire.org -l bandit0 -p 2220
```
If you're using Windows, though, you won't find an SSH client by default. While there are several great SSH clients available for use in Windows environments, I like PuTTY since it is straightforward and relatively compact. 

<p align="center">
  <img width="452" height="437" src="https://user-images.githubusercontent.com/84661482/132094175-36de91a1-df1b-413f-af47-54a7e660dcc5.png">
</p>

When you're finished, hit "Open," and you'll be able to access the bandit0 shell. 

![image](https://user-images.githubusercontent.com/84661482/132094368-4fb40674-9827-4514-ad0c-2d2dabbb62c6.png)

## :triangular_flag_on_post: Bandit Level 0 - 1

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

### Summary
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
 ```
The password to level 1 box is **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**

## :triangular_flag_on_post: Bandit Level 1 - 2

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132095632-36c26f4f-fb81-4d88-b24e-a99d61969ad7.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132095451-5e70e4bb-ee33-4120-b751-61495d4f9a88.png)

### Explanation:
To acquire the password for stage 2, we have to print the content of the file called – (a dash sign), as recommended by the hint.

If you just use the **cat** command to read and print the contents of the file called – (a dash sign), unfortunately, your terminal will become stuck. 

![image](https://user-images.githubusercontent.com/84661482/132095836-3a04ea80-ed4a-4e20-b2b6-a7a0bd326dc3.png)

When **cat** encounters the filename – (a dash symbol), it interprets it as a synonym for **STDIN**. You must supply the full path of the file rather than just the file name to avoid being regarded as an **STDIN** and your terminal getting nothing. 

### Summary
```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
The password to gain access to level 2 box is **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**

## :triangular_flag_on_post: Bandit Level 2 - 3

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

### Summary
```
bandit2@bandit:~$ ls 
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
The password to gain access to level 3 box is **UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK**

## :triangular_flag_on_post: Bandit Level 3 - 4

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132096510-977f84a2-01ec-4a5c-b212-ca68d47fb5b8.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132096604-c0ef8903-b5a0-40e7-bac3-48e62c6d5184.png)

### Explanation:
Because the file is hidden, just use **ls -a** to find it. To learn about how the flags such as **-a** or **-l** work, you can use **man ls**.

![image](https://user-images.githubusercontent.com/84661482/132096705-30315891-0053-4728-9e45-ac203ebbf252.png)

### Summary
```
bandit3@bandit:~/inhere$ ls -al
total 12
drwxr-xr-x 2 root    root    4096 May  7  2020 .
drwxr-xr-x 3 root    root    4096 May  7  2020 ..
-rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
The password to gain access to level 4 box is **pIwrPrtPN36QITSp3EQaw936yaFoFgAB**

## :triangular_flag_on_post: Bandit Level 4 - 5

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
We're basically using **find** (read the manpages if you don't understand the command) to get the **full paths** of all files in the current directory, and then passing those paths as **STDIN** to the **file** command, which will return the file type. The **xargs** command is used to perform the **file** command for each line. We'll know the human-readable file is "./-file07" this way, and then we're going to be able to **cat** the password directly from it.

### Summary
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
The password to gain access to level 5 box is **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**

