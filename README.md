This is the startup of the IUCTF group's repository. The github pages are available at http://iuctf.github.io/

Our github pages are integrated with [jekyll](https://jekyllrb.com/docs/installation/) to update them in between the github server and local machines asynchronously.

[github markdown syntax](https://guides.github.com/features/mastering-markdown/)

A quick instruction of adding/updating new github page(s):
1. ```git clone git@github.com:iuctf/iuctf.github.io.git```
2. `cd notes`
3. If you do not have a direct instruction page of your tool, create one by copying one of the other pages (e.g. unicorn_blog.html, keystone_blog.html, ...)
  * make sure that you add the following meta data part to your page
```
---
layout: blog
category: unicorn
---
```
4. `cd _posts` and create a directory representing your tool.  
For example,
`mkdir unicorn`  
If it already exists, just change a directory to it
5. Create a instruction file for a topic that you want to write about with a specific format.  
For example, the page for the introduction of unicorn should be named with the following format:  
`yyyy-mm-dd-<topic-name>.md` ==>
`2017-05-23-introduction-to-unicorn.md`  
Please refer to the `unicorn/2017-05-23-introduction-to-unicorn.md` to see how the metadata part is added.
6. Check your changes in jekyll
  * If you have not setup jekyll in your local machine, please follow these instructions:
     1. `gem install jekyll bundler`
     2. `bundle install`
     3. `bundle exec  jekyll serve`
  * Check to see how your changes work in your local machine via http://127.0.0.1:4000/notes/
7. Once you are happy with all your changes, add them to the repository:  
   `git status` && `git commit -a` && `git push`

[Basic instruction of github + jekyll](https://github.com/pages/jekyll) 
