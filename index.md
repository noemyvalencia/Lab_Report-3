# Command FIND
by Noemy Valencia

---

There are multiple ways to use the command find in out terminal to, well, find anything from anywhere we want. Next, we will be discussing 4 different implementations of this command, in this case, in our directory `technical`.

## First implementation: 
This use of find is very simple, since we only need the name of the directory to see what's inside.

In this case, `technical` has some directories, like `biomed` and `plos`.
1. Running the command `find technical -mtime -1`, we get all the files in technical that have been modified less day a day ago.
```
Noemys-MacBook-Air:docsearch noemyvalencia$ find technical -mtime -1
technical
technical/.DS_Store
technical/911report
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```
This is a very uselful command when we've been working on different files and want easy access in case we need to go back and fourth, saving a lot of time.


2. Same way, running `find technical/911report -mtime +1`, we get all the files in technical/911report that have been modified more than a day ago.
```
Noemys-MacBook-Air:docsearch noemyvalencia$ find technical/911report -mtime +1
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
technical/911report/chapter-12.txt
```
The same thing happens here, it's useful to find all the files that have been modified under or over a certain time of our choosing for easy access, especially if we know the directory where it's stored too.

## Second implementation: 
This use of the command is finding a file with a keyword in the last part of its name, for example:

1. Running the command `find technical -name "*29.txt"`, returns all the files in technical ending in said string.
```
noemyvalencia@Noemys-MacBook-Air docsearch % find technical -name "*29.txt"
technical/government/Gen_Account_Office/og98029.txt
technical/plos/pmed.0010029.txt
technical/plos/journal.pbio.0030129.txt
technical/biomed/1471-2164-3-29.txt
technical/biomed/cc1529.txt
technical/biomed/1471-2334-2-29.txt
technical/biomed/1471-2180-1-29.txt
technical/biomed/ar429.txt
technical/biomed/gb-2002-3-6-research0029.txt
technical/biomed/1471-2180-2-29.txt
```
This implementation is very uselful in cases of extension, it facilitates finding a certain file just by looking up its extension.

2. Also, running `find technical -name "*11.txt", returns all the files ending in 11.txt.
```
noemyvalencia@Noemys-MacBook-Air docsearch % find technical -name "*11.txt"
technical/government/Gen_Account_Office/og96011.txt
technical/government/Gen_Account_Office/og97011.txt
technical/plos/journal.pbio.0020311.txt
technical/biomed/1471-2156-3-11.txt
technical/biomed/1472-6750-3-11.txt
technical/biomed/1471-2091-2-11.txt
technical/biomed/gb-2001-2-4-research0011.txt
technical/biomed/1471-2121-3-11.txt
technical/biomed/1471-2202-4-11.txt
technical/biomed/1472-6750-1-11.txt
technical/biomed/1471-2407-2-11.txt
technical/biomed/1475-925X-2-11.txt
technical/biomed/gb-2003-4-2-r11.txt
technical/biomed/1471-2458-2-11.txt
technical/biomed/1471-2180-3-11.txt
technical/biomed/1472-6793-2-11.txt
technical/biomed/1472-6963-3-11.txt
technical/biomed/1471-2199-3-11.txt
technical/biomed/1471-2121-2-11.txt
technical/biomed/1471-2288-2-11.txt
technical/biomed/1471-2350-2-11.txt
technical/biomed/1472-6963-1-11.txt
technical/biomed/1472-6882-1-11.txt
technical/biomed/1471-2334-3-11.txt
technical/biomed/1475-2883-2-11.txt
technical/biomed/1472-6793-1-11.txt
technical/biomed/1471-2202-3-11.txt
technical/biomed/1471-2261-2-11.txt
technical/biomed/1471-2229-2-11.txt
technical/biomed/1471-2431-2-11.txt
technical/biomed/1471-2458-3-11.txt
technical/biomed/gb-2002-3-3-research0011.txt
technical/biomed/1471-213X-1-11.txt
technical/911report/chapter-11.txt
```
It is also uselful when we know the ending of the filename apart from the extension, and could help narrow down to very few files.

## Third implementation: 
For this use, we find what we want depending on its category, for example:

1. By running `find technical -type d` we get all the directories inside of technical.
```
noemyvalencia@Noemys-MacBook-Air docsearch % find technical -type d
technical
technical/government
technical/government/About_LSC
technical/government/Env_Prot_Agen
technical/government/Alcohol_Problems
technical/government/Gen_Account_Office
technical/government/Post_Rate_Comm
technical/government/Media
technical/plos
technical/biomed
technical/911report
```

I find this very useful since we dont have to acces the directory to know what's inside, and they try to figure out if they're directories or files.

2. And by running `find technical -type f` we get all the regular files from technical (which are a lot to fit in the screen, but it's a long list that loos like the following).
```
noemyvalencia@Noemys-MacBook-Air docsearch % find technical -type f
[...]
technical/plos/pmed.0020068.txt
technical/plos/journal.pbio.0020012.txt
technical/plos/pmed.0020281.txt
technical/plos/pmed.0020242.txt
technical/biomed/1472-6807-2-2.txt
technical/biomed/1471-2350-4-3.txt
technical/biomed/1471-2156-2-3.txt
technical/biomed/1471-2156-3-11.txt
technical/biomed/1471-2121-3-10.txt
technical/biomed/1471-2172-3-4.txt
technical/biomed/gb-2002-4-1-r2.txt
technical/biomed/gb-2003-4-6-r41.txt
[...]
```

Although it is a very long output, it helps us distinguish what's inside of a directory and tell them apart from other categories.

## Fourth implementation:
Lastly, this fourth use is searching what we want by its size.

1. After running `find technical -type f -size -1k` we get all the regular files less than 2 kilobytes inside of technical.
```
noemyvalencia@Noemys-MacBook-Air docsearch % find technical -type f -size -1k
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020226.txt
```

I really like this command because I find it very uselful when we're trying to narrow down to certain files, like needing a picture that can only be a certain size.

2. Same way, changing the command a little to, `find technical -type f -size -2k`, we can see that we get a little more output as we're expanding the search.
```
noemyvalencia@Noemys-MacBook-Air docsearch % find technical -type f -size -2k
technical/government/Media/Helping_Hands.txt
technical/government/Media/Campaign_Pays.txt
technical/government/Media/Fire_Victims_Sue.txt
technical/government/Media/Court_Keeps_Judge_From.txt
technical/government/Media/It_Pays_to_Know.txt
technical/government/Media/Self-Help_Website.txt
technical/government/Media/Justice_requests.txt
technical/government/Media/Wilmington_lawyer.txt
technical/government/Media/Lawyer_Web_Survey.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020226.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020120.txt
```

Also, not only does it let us find by size, but we can include a different category and look up a certain size.

---

I found some of my commands from [Link](https://linuxhostsupport.com/blog/how-to-search-files-on-the-linux-terminal/), however, there are many more to try!

