# README

##### Getting started with Ruby

http://rubyonrails.org/
http://guides.rubyonrails.org/


```
gem install rails
rails new sophie
cd sophie
bundle install
rails server
```

Browser visit here: http://localhost:3000

Control-C to stop server

##### Gemfile libraries

"Gemfile" - contains all the libraries

##### Local git repository

```
git init
git status
```
	"Untracked" - git doesn't know about these files or directories

```
man git-add
git add --help
git add Gemfile* app bin config.ru config lib public/ vendor/
alias ga='git add'
```

Also see Atlassian SourceTree <https://www.sourcetreeapp.com/>

```
git add db/seeds.rb
git commit
```

"vi" - Unix text editor (nano, vim)

 - i = insert
 - x = delete a character
 - ESC = cancel
 - :w = save
 - :q! = quit without saving
 - :q = quit
 - :wq = save and quit
 - :help = help!
 - :q = exit help

```
git commit -m "Initial Rails install"
```

```
Nigel-MBP:sophie wtfiwtz$ git log
commit 7e22754db368a0b7f4956d1ade5343e4935e361d
Author: Nigel Sheridan-Smith <wtfiwtz@gmail.com>
Date:   Sat Aug 6 15:06:46 2016 +1000

    Initial Rails install
```

```
git status
git log --stat # list files in each commit
```

```
Nigel-MBP:sophie wtfiwtz$ pwd
/Developer/sophie

Nigel-MBP:sophie wtfiwtz$ cd app
Nigel-MBP:app wtfiwtz$ pwd
/Developer/sophie/app


Nigel-MBP:app wtfiwtz$ cd ..
Nigel-MBP:sophie wtfiwtz$ pwd
/Developer/sophie
```

#### Generating a "static" controller

```
rails generate controller Static
```

creates file ./app/controllers/static_controller.rb


#### Unix commands, and 'brew'

Brew installer: http://brew.sh/

```
"brew install nano"
brew install mysql-server
brew install postgresql
brew install apache2
```

```
Nigel-MBP:sophie wtfiwtz$ ps aux | grep rails
wtfiwtz         21770   0.0  0.0  2434840    776 s002  S+    3:30pm   0:00.00 grep rails
wtfiwtz         18701   0.0  0.1  2477792  19860 s001  S+    3:20pm   0:00.56 /Users/wtfiwtz/.rvm/rubies/ruby-2.2.3/bin/ruby bin/rails generate controller Static
```

```
Nigel-MBP:sophie wtfiwtz$ sudo kill -9 18701
Password:
```


```
Nigel-MBP:sophie wtfiwtz$ sudo bash
bash-3.2# exit
exit
```

```
Nigel-MBP:sophie wtfiwtz$ cd ~
Nigel-MBP:~ wtfiwtz$ pwd
/Users/wtfiwtz
```


```
# REMOVING FILES - DANGEROUS!
Nigel-MBP:sophie wtfiwtz$ rm -Rf /Developer/sophie/log/*
```

```
# Rails preloading
Nigel-MBP:sophie wtfiwtz$ spring stop
```


#### Create a controller action

```ruby
class StaticController < ApplicationController   
  def index   
  end 
end 
```

 http://localhost:3000/static/ => app/views/static/index.html.erb (ERB) http://localhost:3000/static/123 => app/views/static/show.slim (Slim templating language)  http://localhost:3000/books/ => list of books http://localhost:3000/books/10 => the 10th book 



app/views/static/index.html.erb

```
<div>    Hello Sophie!  </div> 
```


config/routes.rb


```
Rails.application.routes.draw do   
  # For details on the DSL available within this file, see http://guides.rubyonrails.org/routing.html    
  root to: 'static#index'  
end 
```

```
ga app/assets/ app/controllers/ app/helpers/ app/views/
git commit -m "Initial static controller"
```


```
Nigel-MBP:sophie wtfiwtz$ git blame config/routes.rb
```



Github repository: <https://github.com/wtfiwtz/sophie>

```
git remote add origin https://github.com/wtfiwtz/sophie
```


```
Nigel-MBP:sophie wtfiwtz$ git remote -v
origin	https://github.com/wtfiwtz/sophie (fetch)
origin	https://github.com/wtfiwtz/sophie (push)
```



```
Nigel-MBP:sophie wtfiwtz$ git push origin master
Counting objects: 100, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (82/82), done.
Writing objects: 100% (100/100), 21.00 KiB | 0 bytes/s, done.
Total 100 (delta 8), reused 0 (delta 0)
To https://github.com/wtfiwtz/sophie
 * [new branch]      master -> master
```


