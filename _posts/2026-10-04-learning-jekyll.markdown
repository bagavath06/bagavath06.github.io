Jekyll:The static site builder
=

## HOW TO

1. How to create a site:  

    * `jekyll new (website-name)`
















## Previewing the website:  

* `bundle exec jekyll serve`

## Fornt matter 

* Information about the post.

* eg title:xyz  
* layout : post
1. What languages the front matter written?
    - JSON and YAML  

## Writing Post
* How to name the file
yyyy-mm-dd-filename.extention
## DRAFT post 
* `mkdir _draft`
* Its will not show in the website
* To see what in draft `jekyll serve --draft`
* you dont need to follow yyyy-mm-dd formart to create the draft
## how to create pages
* simple create  a file 
* eg `touch donation.md`
* In front matter add `layout:page` 
## How to create a permenent url
* In front matter add `premalink:"url"`
* can also use as variable  
* eg: categories: jekyll
*` permalink:/:categories` the semi collen matter
## Making Front-matter deafult 

* go to config files
* add `defaults:`
```
defaults:
   - 
   scope:
     path: "" #apply to all by empty string you can also specficy.
   values: 
      layout : "post"
after doing confi restart the jekyll
you can also specific the type
why bcz if you do the empty string its will also apply for layout : pages too 
we dont cant that so 
type: "post"
```
## Changing the theme 
1. choose a theme from ruby.org
2. search for jekyll theme. 
3. select a theme and look for homepage. 
4. put it into gemfile 
5. and run `bundle install` it will install the theme.
## Layout 
1. create a folder _layouts
2. inside layout post.html
3. {{content}}

this test == high ==  

    print("hello")
This is normal paragraph text.

\*italic\*


    
    


    