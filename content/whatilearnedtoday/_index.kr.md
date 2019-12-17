+++
title = "What I learned today"
date = 2019-11-02T22:03:35-04:00
weight = 2
chapter = true
pre = "<i class='fas fa-calendar-day'></i>  "
+++

### What I learned today

Dairy learning note from 2019

___
#### 2019 December


###### 20191218

1. console.table()
`console.table();` show console log more beautiful when you want to see `object` or `array` in your browser console.

ex) `console.table(iamobject);`

It shows this console log!
![console.table(](http://areuman.work/wp-content/uploads/2019/12/consoletable.png)

2. my commit not showing up on my profile in github

I realized my commit didn't show my github profile after I changed my computer. 

It was because 
my email address in gitconfig file and github website setting was different.

you can edit your address in gitconfig.
`git config --global --edit`

If you need more information, [check github site](https://help.github.com/en/github/setting-up-and-managing-your-github-profile/why-are-my-contributions-not-showing-up-on-my-profile "check github site")



___
#### 2019 November

###### 20191109

1. Install bitnami with codeIgniter, laravel and symfony
[install bitnami](https://docs.bitnami.com/bch/infrastructure/lamp/get-started/use-codeigniter/)
2. Learn MVC
3. Learn codeIgniter
4. Create CI blog - [Git](https://github.com/AreumAn/Study_PHP_frameworks/pull/1)

**MVC**

- Model : Data - db, api calls
- View : Displayed through the browser - HTML
- Controller : Bridge between the model and view.

controller will determine what to do by user request.
Router checks the HTTP request and decides which controller will be used to handle the request.

**codeIgniter**

Found this PDF and learned from it!
Check it out if you want more detail about codeIgniter.
[go to learn codeigniter](http://mfikri.com/en/blog/codeigniter-tutorial)

**What is codeigniter?**

Codeigniter is a Web Application PHP Framework designed specifically to
facilitate web developers in developing web-based application.
Codeigniter contains a collection of code in the form of libraries and tools combined into a framework.

Codeigniter use the Model-View-Controller (MVC) design or architecture pattern that separates the code portion for business process handling with code sections for presentation purposes.

**Advantages**

1. Small size framework
2. Open source
3. Model-View-Controller (MVC) design pattern:  easier to read,
understand, and maintain
4. Can be expanded as needed.
5. Well-documented information
6. A complete library and helper
7. Reliable security such as xss filtering, session encryption, and others
8. Allows web developers to use libraries or helper not provided by
codeigniter like: Google Map API, Facebook API, and others.
9. Basically embraces Clean URL and supports SEO. So that, the application built using codeigniter is easier to index by popular search engines like google.

**Basic Files**

- **application/config/autoload.php** : set the functions to auto load at the beginning(packages, libraries, drivers, helper files, custom config files, language files, and models)
- **application/config/config.php** : base_url, index_page and encryption_key
- **application/config/database.php** : database configuration

**troubleshoot**

- error

```
Undefined property: Product::$db
```
- solution: `$autoload['libraries'] = array('database');. ` in autoload.php











