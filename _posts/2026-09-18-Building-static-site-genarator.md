---
layout: post
title: group-project-1
date: 2026-09-22
categories: jekyll update
---
**Course.** *Craft of Computing*     
**Group Number.** *Group 3*  
**Group Member.** *Group 3: Joe Akash, Nithish N, Bagavath B*

---

## What was the project about:
To build a static site genator using bash shell scripting 
## Our task during the project and how I  approached  :
1.  **Markdown To HTML Convertion**:Using bash script and pandoc tool we are able to Convert a directoty of .md files into html files.
 - The arguments are very usefull during the script writing. i used "$" symbol for getting input.
 - My  approched for this, first i removed the extension(.md) using basename and then i added the html extentiont
 - I  used for loop with the * operator which will look for all file inside the directory which are md file so later i can convert into html using the basename.
 - cd "$1" this idea i get from bavana. it will go into that director, which is our first argument  and so the for loop will check the files inside that directory. 
 - 'for file in "$1"/*.md;'
 - 'base=$(basename "$file".md )'#this how is used the basename to remove the .md extention 

1. **Support layout** : I used AI for this part completly so I am not fimiliar how this works.  
1. **(Copy Other Files)** : Automatically scans for non-markdown file   such as   ( images, PDFs, or anything) and mirrors  them directly into the `html/` output directory using `cp`.
  - So cd $1 will check for the specfic directory. so I only need to check the files which are non- markdown in that particular directory 
  - You may have a case where the directory may contain another directory in it. so we have to check only the files in the specific directory.
  - First we have provied the sourse directory which is "$1". we can also store  the sorce directory by a variable. a="$1"
  - cd $1 will not work here bcz to put non-markdown file in html/ you are inside a specific directory where the html/ directory may not exsist. so we have to direct the relative path for the output. if that html/ not exist. it need to create by automatic. mkdir -p , -p will not give error if the directory already exist.  
  - targetdirect="$(pwd)/html"
  - mkdir -p "$targetdirectory"
  - cd "$1"
  - for file in *; do if [[ -f "$file" && != "$file"/*.md ]]; then 
  - cp "$file" "$targetdirectory/"

1. **Error Handling**  : If the arguments are not passed.The script stops.It will ask to provide the argument. If a argument is not valid,script stop and ask to provide the vaild argument. the provied argument have no markdown file it will show no markdown file. It will show error if the pandoc is not installed.
  - ERROR-1: ./build.sh <empty-argument> so I used if there was empty string in $1 it need to give error. so if [ "$1" == "" ]; then echo "provide the argument"
  - ERROR-2: ./build.sh <not-valid-argument> check the $1 id there or not if [! -d $1 ]; then provide a vaild argument 
  - ERROR-3 what if the $1 have no markdown files. while doing ls if there is no makrdown files give error. if ! ls "$1"/*.md ; 
  - ERROR-4 i solved this with which pandoc will give the version of it so. when excuteing if pandoc if i get nothing. that means pandoc not installed. if [ $(whichpandoc) == ""]; 

## Which order I done my project 
1. We first started with Error Handling. We did all the four error handling with the if the statements .**Error-1** Not provied argument, so we relate the if condition with the empty string.  So If a argument with empty string Its will stop the script and Ask  to enter the argument.**Error-2** Not provided  a valid argument. we used logical invert operator for this ! and -d option. -d will check Its a vaild arguments or not. if not the error pop. ask for valid directory. **error-3** The given vaild argument have no md files. we  again used logical invert operator and ls *.md to solve this error. **error-4** pandoc not installed- we used which  commment and compare with empty string to solve this error 

2. Convertion of Markdown files to html files and Suppot layout.
We used For Loop, and if else condition to do this. first with for loop we found all the md files in the directory and removed the extention of .md with the keyword basename. Then with the if else condition the support layout was done. If there was no layout files then we used pandoc tool to convert markdown files into html files.

3. For copy other files and put into html directoty we used for, if condition, and some logical operator- AND and NOT. first we check its is a file because we dont want directory. then by ls with NOT logic we can find the non markdown files. then it will be copied to the html directory.

4. Skip if the html files is newer than markdown file. first with the if condition I checked Wheater it is a file then. with logical operator i checked the html file is newer than markdown file. then skip if it is newer with the continue. for checking files. I  aslo used "for loop".  

5. The script uses an if statement to check if the file path starts with the folder name _posts/*. Depending on the answer, it extracts the file's name and glues it together with text to build the final folder and .html destination path.

6. The script uses head -n 1 to grab the first line and uses the # operator to slice off the leading markdown characters. It then passes that extracted text into the --metadata title= parameter of the Pandoc command-line utility to inject it into the final output.
## Additional feature
1. Skip a file whose html is newer than its Markdown
2. Feature takes the first heading of a Markdown file and uses it as the title of the HTML webpage.
3. Treat _posts/ as a blog: each markdown file in it becomes
html/posts/<name>.html

## Group Members and Contributions
* **[Bagavath B]:** ALL Main feature, README.md, One additional feature- Skip a file whose html is newer than its Markdown.
* **[Joe Akash]:** ONE additional feature, Feature takes the first heading of a Markdown file and uses it as the title of the HTML webpage.
* **[Nithish N]:**. ONE  Additional feature - Treat _posts/ as a blog: each markdown file in it becomes

## Things I learned from this Group-Project-1
* I was so depended on AI, even for simple error handling I used AI for do it.
* All are simple basic if you know to merge them you can solve the problems that create 


