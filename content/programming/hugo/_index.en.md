+++
title = "Hugo"
date = 2019-06-30T15:47:52-04:00
weight = 11
chapter = true
pre = "<i class='far fa-window-maximize'></i> "
+++

### Hugo
***

+ [Commands](#hugo-commands)
+ [Google Analytics](#web-crawler)


<a name="hugo-commands"></a>
### Commands for Hugo
___
**Create new project**
```
hugo new site <new_project>
```
**Create new category**
```
hugo new --kind chapter {your category name}/_index.md
```
**Launching the website locally**
```
hugo serve
```

<a name="google-analytics"></a>
### Google Analytics
___

There are some steps you need to do.

* **Set up Google Analytics Account and Property for your site.**

[go to google analytics site](https://analytics.google.com)
![get track ID](https://drive.google.com/uc?id=1vqpvwbcsPAK6TWTLI9tj8oHIYGKQ4m8V)

* **Add unique Tracking ID for your site to your Hugo site's config file.**
![Copy track ID](https://drive.google.com/uc?id=1NotZSb6BYOQBqAFJVYQGffksQ4nrJ9ys)

Add track ID into `config.toml`
```
languageCode = "en-us"
title = "Areum Blog"
theme = "hugo-theme-learn-master"
googleAnalytics = "{{YOUR TRACKING CODE}}"
```

* **Enabled the internal Hugo template for Google Analytics in your overwrited header files.**

Make new overwirte header html files `/layouts/partials/header.html`
From `/themes/hugo-theme-learn-master/layouts/partials/header.html`

Add google analytics in head tag. Above `</head>`
```
    {{ template "_internal/google_analytics.html" . }}
</head>
```

* **Test with your local**

1. Server up
2. open your website with local address(localhost:1313)
3. go to [https://analytics.google.com](https://analytics.google.com)
4. Check active user and `real-time> content menu`


