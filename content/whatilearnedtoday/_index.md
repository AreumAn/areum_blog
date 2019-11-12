+++
title = "What I learned today"
date = 2019-11-02T22:03:35-04:00
weight = 2
chapter = true
pre = "<i class='fas fa-calendar-day'></i>  "
+++

### What I learned today

Dairy learning note from 2019 november

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



---

###### 20191110

1. Finish Create CI blog - update product [Git](https://github.com/AreumAn/Study_PHP_frameworks/pull/2)
2. JS - codewar trainingJS(10-20)

**[[ Javascript ]]**

**slice()**
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

```js
arr.slice([begin[, end]])

var animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]

console.log(animals.slice(1, -1));
// Array ["bison", "camel", "duck"]

console.log(animals.slice(-1));
// Array ["elephant"]

console.log(animals.slice(-2));
// Array ["duck", "elephant"]
```

**substring()**
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)

```js
str.substring(indexStart[, indexEnd])

var str = 'Mozilla';

console.log(str.substring(1, 3));
// expected output: "oz"

console.log(str.substring(2));
// expected output: "zilla"
```

**substr()**

Warning: Although String.prototype.substr(…) is not strictly deprecated (as in "removed from the Web standards"), it is considered a legacy function and should be avoided when possible. It is not part of the core JavaScript language and may be removed in the future. If at all possible, use the substring() method instead.

**The difference between `substring()` and `substr()`**
```js
var text = 'Mozilla';
console.log(text.substring(2,5)); // => "zil"
console.log(text.substr(2,3));    // => "zil"
```

**Differences between `substring()` and `slice()`**
```js
var text = 'Mozilla';
console.log(text.substring(5, 2)); // => "zil"
console.log(text.slice(5, 2));     // => ""

console.log(text.substring(-5, 2)); // => "Mo"
console.log(text.substring(-5, -2)); // => ""

console.log(text.slice(-5, 2)); // => ""
console.log(text.slice(-5, -2)); // => "zil"
```

**split()**
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)

```js
str.split([separator[, limit]])

var str = 'The quick brown fox jumps over the lazy dog.';

var words = str.split(' ');
console.log(words);
// Array ["The", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog."]

var chars = str.split('');
console.log(chars);
// Array ["T", "h", "e", " ", "q", "u", "i", "c", "k", " ", "b", "r", "o", "w", "n", " ", "f", "o", "x", " ", "j", "u", "m", "p", "s", " ", "o", "v", "e", "r", " ", "t", "h", "e", " ", "l", "a", "z", "y", " ", "d", "o", "g", "."]

var strCopy = str.split();
console.log(strCopy);
// Array ["The quick brown fox jumps over the lazy dog."]


var words = str.split(' ', 3);
// Array ["The", "quick", "brown"]

```

**join()**
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

```js
var elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(''));
// expected output: "FireAirWater"

console.log(elements.join('-'));
// expected output: "Fire-Air-Water"
```


---

###### 20191111

1. JS - this

**this** is an object in most of situation.

**1) Regular function call :**

'this' === global object (window object in browser)

```js
function foo () {
    console.log(this);
}
foo();
```

```js
var age = 100;

function foo() {
    var age = 99;
    bar();
}

function bar() {
    console.log(this.age); // 100
}

foo();
```

**2) Dot Notation**

```js
var age = 100;
var areum = {
    age: 35,
    foo: function foo() {
        console.log(this.age); // 35
    },
}
areum.foo();
```

```js
function foo() {
    console.log(this.age);
}

var age = 100;

var areum = {
    age: 35,
    foo: foo,
};

var momo = {
    age: 30,
    foo: foo
};

areum.foo();    // 35
momo.foo()      // 30
```

**3) Function.prototype.call, Function.prototype.bind, Function.prototype.apply**

```js
var age = 100;

function foo() {
    console.log(this.age);
}

var areum = {
    age: 35,
};

var momo = {
    age: 30,
};

foo();  // 100

foo.call(momo); // 31
foo.apply(ken); // 35
```

```js
var age = 100;

function foo() {
    console.log(this.age);
}

var areum = {
    age: 35,
};

var = foo.bind(ken);
bar(); // 34
```

**4) 'new' keyword**

```js
function foo() {
    console.log(this);
}

new foo();
```

```js
function foo() {
    this.name = 'areum';
}

var toronto = new foo();

console.log(toronto);
```
