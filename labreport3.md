# CSE 15L Lab Report 3 - Researching Commands (Week 3)
**Melanie Haro** <br />
**A17390371** <br />

The **find** command is an incredibly useful command to find certain files and directories and not just by its file name. Here is an example of me running the find command in a zsh terminal window: <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%206.24%20PM.jpeg)
Here I am in my working directory and used the find command to look for directories with the word "Documents" and as you can see I have a long list of different subdirectories and files with "Documents" in their path. <br />

There are many other alternative commands to find, my personal favorite being **fd**. It is a more evolved alternative to find and it is written in Rust. Its intention was to have a friendlier approach to the find command with better user interface and faster performance. However, it is a command you have to install. I installed it using [Homebrew](https://brew.sh/). Homebrew is a package manager and you can download lots of cool packages on there! Some of the cool ones I have gotten access to include **cmatrix** which just does the following: <br />
![Image](https://raw.githubusercontent.com/melanieharo22/cse15l-lab-reports/main/Image%205-7-23%20at%206.41%20PM.jpeg) <br />

and **neofetch** <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%206.39%20PM.jpeg) <br />
Which basically shows a ton of information about the device you are on. Many Linux users use this to flex their Linux distros. <br />
Back to the actual lab report though, I used brew to install the very useful **fd** command. I already had brew downloaded on my Mac, but to download it you copy the link on their homepage onto your clipboard, paste it into your terminal, and hit enter. If you want to check if you already had it installed, you can simply type **brew -v** to check what version you have installed. For instance, here I am checking for the version I have: <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%206.30%20PM.jpeg)

After installing brew, to install a command or package you would simply type **brew install** and then whatever it is you want to download. In this case, we want the **fd** command. <br /> 
```
brew install fd 
```
It should look something like this: <br /> 
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%205.52%20PM.jpeg) <br />

Here is me using the **fd** command with files and directories from **./technical**: <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%206.12%20PM.jpeg) <br />
As you can see I looked for files with "chapter" in their name. This could be useful if you are looking for a certain chapter within a directory instead of having to manually do it. <br />

Here I looked for anything with **txt** in their name: <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%206.57%20PM.jpeg) <br />
This could be useful if your looking for txt files in case you want to cat them and see their contents. <br />

Another useful alternative to **find** is **mdfind**. This one works a replacement by default, so no need to install anything beforehand. Here I am typing **mdfind biomed** to find any file with biomed in its content. This can be useful if you are looking for specific files with a key word in them. In this case lets say I was working on a biomed project and wanted to see every document in my home directory with the biomed keyword. <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%207.07%20PM.jpeg) <br />

Here I used **mdfind ucsd-cse15l** to look for a file/directory with the keyword "stringsearch-data". This would be useful if you are trying to find the repository you cloned from practicing for Skill Demo 1 or any file/directory containing a very specific keyword. <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%209.30%20PM.jpeg) <br />


The last *interesting* alternative to **find** I came across was the **ripgrep (rg)** command and at first I am not going to lie, it scared me and I thought I broke my computer. I asked ChatGPT ways I can use ripgrep and the first thing I tried was: <br />
```
rg example --type txt

```
This searched for the word "example" only in files with a specific extension (e.g., .txt) and it gave me a ton of output (way too much) so I only took a screenshot of a bit. This seems like a pretty inefficient version of find since it gave me WAY too much information. However, if you use **command F** you can look for anything, but it might take a while and defeats the purpose of even using the command. It might work if you have a super duper unique word. Here is what it looked liked when I typed the command I shared above: <br />
![Image](https://github.com/melanieharo22/cse15l-lab-reports/blob/main/Image%205-7-23%20at%209.44%20PM.jpeg)

Citations: <br />
overall: [Homebrew Documentation](https://docs.brew.sh/) <br />
fd -> [sharkdp/fd](https://github.com/sharkdp/fd) <br />
mdfind -> [mdfind: A Command-line Interface to macOS's Spotlight](https://metaredux.com/posts/2019/12/22/mdfind.html) <br />
locate -> [Enable and Use the ‘locate’ Command in the Mac OS X Terminal](https://osxdaily.com/2011/11/02/enable-and-use-the-locate-command-in-the-mac-os-x-terminal/) && [locate command in Mac | find files and directories using locate in Mac terminal](https://youtu.be/lhwp5QfqmhE)<br />
ripgrep -> [BurntSushi/ripgrep](https://github.com/BurntSushi/ripgrep) && ChatGPT by asking about ripgrep examples :)
