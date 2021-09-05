# :shipit: OverTheWire: Bandit, Level 0-15 Writeup

![image](https://user-images.githubusercontent.com/84661482/132093151-7b225882-2b7c-4973-8150-4df05617ea59.png)

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

![image](https://user-images.githubusercontent.com/84661482/132094175-36de91a1-df1b-413f-af47-54a7e660dcc5.png)

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
The password to the level 1's
box is **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**


## :triangular_flag_on_post: Bandit Level 1 - 2

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132095632-36c26f4f-fb81-4d88-b24e-a99d61969ad7.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132095451-5e70e4bb-ee33-4120-b751-61495d4f9a88.png)

### Explanation:
To acquire the password for stage 2, we have to print the content of the file called **–** (the dash symbol), as recommended by the hint.

If you just use the **cat** command to read and print the contents of the file called **–**, unfortunately, your terminal will become stuck. 

![image](https://user-images.githubusercontent.com/84661482/132095836-3a04ea80-ed4a-4e20-b2b6-a7a0bd326dc3.png)

When **cat** encounters the filename **–**, it interprets it as a synonym for **STDIN**. You must supply the full path of the file rather than just the file name to avoid being regarded as an **STDIN** and your terminal getting nothing. 

### Summary
```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
The password to gain access to the level 2's box is **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**


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
The password to gain access to the level 3's box is **UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK**


## :triangular_flag_on_post: Bandit Level 3 - 4

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132096510-977f84a2-01ec-4a5c-b212-ca68d47fb5b8.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132096604-c0ef8903-b5a0-40e7-bac3-48e62c6d5184.png)

### Explanation:
Because the file is hidden, just use **ls -a** to find it. To learn about how flags such as **-a** or **-l** work, you can use **man ls**.

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
The password to gain access to the box in level 4 is **pIwrPrtPN36QITSp3EQaw936yaFoFgAB**


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
The password to gain access to the level 5's box is **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**


## :triangular_flag_on_post: Bandit Level 5 - 6

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

### Summary
```
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
The password to gain access to the level 6's box is **DXjZPULLxYr17uwoI01bNLQbtFemEgo7**


## :triangular_flag_on_post: Bandit Level 6 - 7

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132099614-4a865824-77e7-4981-b764-42aa64509734.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132099916-9dfc58cc-e781-4fce-af20-28021f84c411.png)

### Explanation:
This level is quite similar to the previous one, which you should have completed using the **find** command by now. However, because the scope of the search includes the entire drive of the computer rather than just 80 files in a folder, we need to provide extra parameters to be more particular in what we want to look for at this level. 
```
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -type f -size 33c
/var/lib/dpkg/info/bandit7.password
```
The above command searches from the **root** directory (the first or top-most directory in the Linux Filesystem Hierarchy Standard), as shown by **the slash (/)** sign right after the **find** command. Other parameters include: 

1. **user**, which defines the file owner, bandit7
![image](https://user-images.githubusercontent.com/84661482/132100440-31da661e-7556-4c90-8648-6da8c82c9322.png)

2. **group**, which defines the file group, bandit6 in this case
![image](https://user-images.githubusercontent.com/84661482/132100463-ee3b00a3-1675-4022-ae14-221ba177ed66.png)

3. **size**, which defines the size of the file. 33c means 33 bytes of characters

### Summary
```
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
The password to gain access to the level 7's box is **HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs**


## :triangular_flag_on_post: Bandit Level 7 - 8

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132100649-9af7bc21-70a6-40e6-9a72-80ef95cca6fd.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132101128-488b6f7c-25f2-4d0d-a61e-fa7d307bafa0.png)

### Explanation:
This level is really rather straightforward and can be completed in a variety of ways, but if you try to get the password by just **cat**-ing the file without doing anything else, you'll quickly regret it since the file includes an endless number of unique strings, making your terminal scroll forever: 

![image](https://user-images.githubusercontent.com/84661482/132101358-9b495607-d703-4b53-8aff-46976a348d72.png)

To stop the terminal from reading the file, press **Ctrl + C**. This powerful command could be able to kill almost every running process in Linux.

So how to solve this level? Personally, I would prefer to simply **cat** the file and then **grep** the keyword mentioned in the hint, “millionth“.

### Summary
```
bandit7@bandit:~$ cat data.txt | grep 'millionth'
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
The password to gain access to the level 8's box is **cvX2JJa4CFALtqS87jk27qwqGhBM9plV**


## :triangular_flag_on_post: Bandit Level 8 - 9

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

![image](https://user-images.githubusercontent.com/84661482/132112815-a3d25195-20b8-4d0e-ab00-8de919d66cf2.png)

In short, we can simply retrieve the unique password line by using the piping technique **|** to combine **sort** and **uniq -u**. 

### Summary:
```
bandit8@bandit:~$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
The password to gain access to the level 9's box is **UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR**

## :triangular_flag_on_post: Bandit Level 9 - 10

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132112961-98c1f971-7a6c-4462-b983-a0f6e1738581.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132113009-97f996a4-759e-46a6-85db-58bb2cb3d18a.png)

### Explanation:
As with previous stages, we must search for the password within a text file. But you can't use the **cat** and **grep** commands since it's a "binary" file instead of a text file, which makes this level tough. 

![image](https://user-images.githubusercontent.com/84661482/132113056-8b617609-b8b9-43af-bbe8-1931ac01d8ea.png)

Try the **strings** command at this point. If you want to know more about what **strings** command does, read its manpage:

![image](https://user-images.githubusercontent.com/84661482/132113094-bdd3811a-3dff-4001-9a99-2e52cb2ac732.png)

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

### Summary
```
bandit10@bandit:~$ base64 -d data.txt 
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

```
The password to the level 11's box is **IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR**

## :triangular_flag_on_post: Bandit Level 11 - 12

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132113678-40623a30-698b-406e-9e1b-e452fc9ff164.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132113748-f2765269-1f49-43b8-a7ab-a53a5ab50768.png)

### Explanation:
As provided in the hint, we are required to perform a ROT13 “decode” on the file given. First, let’s look at the clue,
```
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh
```
Now, we can decode this using any decoding tool that you like. I myself use [CyberChef](https://gchq.github.io/CyberChef/)

![image](https://user-images.githubusercontent.com/84661482/132115018-89618cea-035d-4ec8-896c-949ac7bbfd8f.png)

However, if you believe solving this problem using a built-in Linux command is sexier, there is a method to imitate the **ROT13** decoding process with the **tr** command: 

![image](https://user-images.githubusercontent.com/84661482/132115119-3a0c3a7b-9b80-480b-9ebb-cff557175410.png)

For this problem, **tr** command is used to translate the first set of characters ‘A-Za-z’ to ‘N-ZA-Mn-za-m’ which is a rotation of 13 positions of the first set.

### Summary
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
This level is one of the most tedious stage in this CTF challenge. First, let’s move the file to a new directory in the **/tmp** folder under your name (create one using the **mkdir** command!).

Copy the data.txt file from **~** to **/tmp/yourusername/**:
```
bandit12@bandit:~$ cp data.txt /tmp/sasha/data.txt
```
Change the working directory to **/tmp/yourusername** using cd:
```
bandit12@bandit:~$ cd /tmp/sasha/
```
Let's see what's in the file using **cat**:
```
bandit12@bandit:/tmp/sasha$ cat data.txt 
00000000: 1f8b 0808 0650 b45e 0203 6461 7461 322e  .....P.^..data2.
00000010: 6269 6e00 013d 02c2 fd42 5a68 3931 4159  bin..=...BZh91AY
00000020: 2653 598e 4f1c c800 001e 7fff fbf9 7fda  &SY.O...........
00000030: 9e7f 4f76 9fcf fe7d 3fff f67d abde 5e9f  ..Ov...}?..}..^.
00000040: f3fe 9fbf f6f1 feee bfdf a3ff b001 3b1b  ..............;.
00000050: 5481 a1a0 1ea0 1a34 d0d0 001a 68d3 4683  T......4....h.F.
00000060: 4680 0680 0034 1918 4c4d 190c 4000 0001  F....4..LM..@...
00000070: a000 c87a 81a3 464d a8d3 43c5 1068 0346  ...z..FM..C..h.F
00000080: 8343 40d0 3400 0340 66a6 8068 0cd4 f500  .C@.4..@f..h....
00000090: 69ea 6800 0f50 68f2 4d00 680d 06ca 0190  i.h..Ph.M.h.....
000000a0: 0000 69a1 a1a0 1ea0 194d 340d 1ea1 b280  ..i......M4.....
000000b0: f500 3406 2340 034d 3400 0000 3403 d400  ..4.#@.M4...4...
000000c0: 1a07 a832 3400 f51a 0003 43d4 0068 0d34  ...24.....C..h.4
000000d0: 6868 f51a 3d43 2580 3e58 061a 2c89 6bf3  hh..=C%.>X..,.k.
000000e0: 0163 08ab dc31 91cd 1747 599b e401 0b06  .c...1...GY.....
000000f0: a8b1 7255 a3b2 9cf9 75cc f106 941b 347a  ..rU....u.....4z
00000100: d616 55cc 2ef2 9d46 e7d1 3050 b5fb 76eb  ..U....F..0P..v.
00000110: 01f8 60c1 2201 33f0 0de0 4aa6 ec8c 914f  ..`.".3...J....O
00000120: cf8a aed5 7b52 4270 8d51 6978 c159 8b5a  ....{RBp.Qix.Y.Z
00000130: 2164 fb1f c26a 8d28 b414 e690 bfdd b3e1  !d...j.(........
00000140: f414 2f9e d041 c523 b641 ac08 0c0b 06f5  ../..A.#.A......
00000150: dd64 b862 1158 3f9e 897a 8cae 32b0 1fb7  .d.b.X?..z..2...
00000160: 3c82 af41 20fd 6e7d 0a35 2833 41bd de0c  <..A .n}.5(3A...
00000170: 774f ae52 a1ac 0fb2 8c36 ef58 537b f30a  wO.R.....6.XS{..
00000180: 1510 cab5 cb51 4231 95a4 d045 b95c ea09  .....QB1...E.\..
00000190: 9fa0 4d33 ba43 22c9 b5be d0ea eeb7 ec85  ..M3.C".........
000001a0: 59fc 8bf1 97a0 87a5 0df0 7acd d555 fc11  Y.........z..U..
000001b0: 223f fdc6 2be3 e809 c974 271a 920e acbc  "?..+....t'.....
000001c0: 0de1 f1a6 393f 4cf5 50eb 7942 86c3 3d7a  ....9?L.P.yB..=z
000001d0: fe6d 173f a84c bb4e 742a fc37 7b71 508a  .m.?.L.Nt*.7{qP.
000001e0: a2cc 9cf1 2522 8a77 39f2 716d 34f9 8620  ....%".w9.qm4.. 
000001f0: 4e33 ca36 eec0 cd4b b3e8 48e4 8b91 5bea  N3.6...K..H...[.
00000200: 01bf 7d21 0b64 82c0 3341 3424 e98b 4d7e  ..}!.d..3A4$..M~
00000210: c95c 1b1f cac9 a04a 1988 43b2 6b55 c6a6  .\.....J..C.kU..
00000220: 075c 1eb4 8ecf 5cdf 4653 064e 84da 263d  .\....\.FS.N..&=
00000230: b15b bcea 7109 5c29 c524 3afc d715 4894  .[..q.\).$:...H.
00000240: 7426 072f fc28 ab05 9603 b3fc 5dc9 14e1  t&./.(......]...
00000250: 4242 393c 7320 98f7 681d 3d02 0000       BB9<s ..h.=...
```

### Summary
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
The password to the level 12's box is **8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL**

