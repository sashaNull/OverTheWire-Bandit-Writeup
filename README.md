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

Level 0 is a welcome gift to get you started with the real difficulties. 

![image](https://user-images.githubusercontent.com/84661482/132093444-428e2ad1-dba7-44ac-be13-ae2561b4ee94.png)

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

## :triangular_flag_on_post: Bandit Level 0 - Level 1

