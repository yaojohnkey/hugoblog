---
title: "Blog Website Construction"
date: 2022-11-21T11:51:53+08:00
author: Y John
tags:
categories:
series:
- Themes Guide
tags:
- Blog
- css
- html
draft: false

---

 # Personal Blog Building

> **brief introduction**

[hugo](https://github.com/gohugoio/hugo/releases) : The blog generation framework used in this article

 -   [github](https://github.com/) : Blog dynamic remote storage warehouse (realize web page dynamic refresh)

 -   [netlify](app.netlify.com) : Web hosting (Publication of web pages)

 -   [Git](https://git-scm.com): Complete the remote warehouse download and push tool


 ## environment construction

 > [R compiled language](https://www.r-project.org/)

 -   Choose a close mirror image
     
 -   Select an installation package for your operating system , and performing the installation


> [R studio](https://posit.co/products/open-source/rstudio/)

-   Download and installation


 > [Hugo](https://github.com/gohugoio/hugo/releases)

 -   You can choose to install it in your own operating system, or you can choose to install it in Rstudio (usually not recommended)

 > [Github](https://github.com/)

 -   Sign up a Github account
   
 -   Create a new repository ( remember to ==Add a README file==)

 > [netlify](netlify)

 -   You can sign in with the github acount

## Blog building

 > There are three ways to do this

### The first way

>#### Open Rstudio

- install.package('blogdown')

>#### The next steps

-  `file` -->`New Project`-->`New Directory`-->selecting `Website using blogdown`among the options.  next, type "Your blog directory name" at `Directory name`and "Your Hugo theme you liked (==Usual format: Author/subject name==)" at `Hugo theme`,at last, choose `Open in new session`-->`Create Project`

-  **now, we already compeleted environment construction and file project for the blog creation**
```R
> blogdown::server()       # preview the blog website  
>  
>  # If you want to change the theme of you blog webits,try doing so  
> blogdown::new_site( theme = "Author/subject name")   
>   
> # -   Finish building your website  
> blogdown::build_site()
> # next step is to publish
```
---

### The second way

- Firstly, copy your github repository's [code](URL) (This is used for cloning and push)  `file` -->`New Project`-->`Version Control`-->`Git`,type your [repository URL](URL) and project directory name
```R
> library(blogdown)  
> blogdown::new_site( theme = "Author/subject name")  
> blogdown::server()  
> blogdown::build_site()
> # next step is to publish
```
---
### The third way
-   This is the simplest of the three methods
```R
> hugo new site "Your blog's name"
> git clone https://github.com/digitalcraftsman/hugo-agency-theme   themes/"theme's name"
> hugo server -t hugo-agency-theme --buildDrafts       # preview
> hugo new posts/blog.md                               # Add a blog
> hugo --theme=hugo-agency-theme --baseUrl="https://lastknightcoder.github.io/" --buildDrafts
> cd public
> ls
> # next step is to publish
```
---
 Now, you can browse public, this folder contains all of your blog website files, [host this folder on [netlify](netlify) and you will be able to see your web blog generated](static). But this requires you to manually refresh the web content, let's try hosting web content on GitHub

 ## Host your website

In this step , You need to use git to do this

 #### open `Git Bash`

 -   设置用户名：git config --global user.name"用户名"
    
 -   设 置 邮 箱：git config --global user.email "邮箱地址"

```Git
> git clone "Your repositroy's URL"  
> ls   
> cd "Your repositroy's name"  
> cp /public/ .  /"Your repositroy's name"  
> ### don't replace README.md  
>   
> git init   
> git add .  
> git commit -m "my first commit"  
> git remote add origin "Your repositroy's URL"  
> git push -u origin master #/(mian)
```

 #### open [netlify](netlify)

 `Add new site`-->`Import an existing project`-->choose GitHub-->selecting your repositroy

 ## Epilogue

 The construction of a blog seems very simple, but we can see a lot of things from it. Its function is simply to give you a rigid website to record learning and memories, and it also reflects your growth. You should fill your blog including your life with efforts and sweat

---
```C
 <u>[netlify]:app.netlify.com<u>
 <u>[URL]:`open repository`-->`code`-->'HTTPS'<u>
 <u>[static]:`open netlify website`--> `Add new site`-->`Deploy manually` just wait a few minutes<u>
```
----------