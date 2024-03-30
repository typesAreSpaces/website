+++
title = "My first post: how to make posts and academic websites using Hugo with the academic theme"
author = ["Jose Abel Castellanos Joo"]
date = 2022-08-13
draft = false
+++

While building this website, I thought it would be convenient to take some notes
of the process so I can recall the necessary steps if I have to start from scratch again. This website was \`rendered\` using the [hugo](https://gohugo.io/) static website generator and a special theme called [academic](https://academic-demo.netlify.app).

Most of the help I got comes from [this post](http://www.statslab.cam.ac.uk/~qz280/post/migrating/); it does a pretty good job describing some technical details of the hugo framework and its organization. Thus, the intention of this post is to provide and overview and quick configuration tips which aren't covered by the aforementioned post.


## Tools {#tools}


### Hugo {#hugo}

This static generator is used for building the main components of the website. Its main features are:

-   Editing using markdown: It uses the go programming language to 'compile' html files from markdown files.
-   'Capable Templating': I understand this as convenient code which enables users to programatically structure websites using special variables within markdown.
-   Extensive selection of themes: As I already mentioned before, we will particularly focus on the academic theme.

Here are some installation options for some operating systems:

-   macOs
    ```bash
    brew install hugo
    ```

-   Windows
    ```bash
    choco install hugo --confirm
    ```

-   Debian/Ubuntu
    ```bash
    sudo apt-get install hugo
    ```

-   Arch Linux
    ```bash
    sudo pacman -Syu hugo
    ```

-   Fedora, Red Hat and CentOS
    ```bash
    sudo dnf install hugo
    ```

-   openSUSE
    ```bash
    sudo zypper install hugo
    ```

-   Solus
    ```bash
    sudo eopkg install hugo
    ```

-   OpenBSD
    ```bash
    doas pkg_add hugo
    ```


### Academic theme {#academic-theme}

The theme focuses on academic settings like portfolios, cvs, resumes, conference websites, etc. The [project](https://wowchemy.com/docs/) is well documented and provides good support for academic needs. For example, the author of the theme provides a tool called [Hugo Academic CLI](https://pypi.org/project/academic/) which can generate publication entries from a bibtex file.

In order to install the theme:

1.  Select the \`Academic Resume\` from <https://wowchemy.com/hugo-themes/>
2.  Click on \`Start with Academic Resume\`
3.  Choose either Github or Gitlab to fork the content of the theme into a git repository
4.  Finish the process by clicking on the 'Save &amp; Deploy' button.

The latter will fork the content of the theme from Netlify. The latter will create a website hosted by Netlify. If you already have a domain, e.g. a personal website or some url from your university, I'd recommed just to keep track of the content from either Github or Gitlab.

<a id="figure--fig:academic-theme-content"></a>

{{< figure src="/ox-hugo/academic_theme_content.png" caption="<span class=\"figure-number\">Figure 1: </span>If you chose the default name, the following repo should appear in your account" >}}


### [Ox-hugo](https://ox-hugo.scripter.co) (optional) {#ox-hugo--optional}

If you're an emacs user who likes org-mode, the ox-hugo package comes handy to organize your posts and use org instead of markdown.

Add the following to your init.el configuration file to obtain hugo:

```emacs-lisp
(with-eval-after-load 'ox
  (require 'ox-hugo))
```

If you use [use-package](https://github.com/jwiegley/use-package), use this instead:

```emacs-lisp
(use-package ox-hugo
  :ensure t   ;Auto-install the package from Melpa
  :pin melpa  ;`package-archives' should already have ("melpa" . "https://melpa.org/packages/")
  :after ox)
```


## Basic customization {#basic-customization}

After cloning your repo into a local machine, your website is ready to be published. You can use the command

```bash
hugo server -D
```

to see a preview of how it would look like.

On the other hand, it can take some time to go through Hugo's documentation to figure out where to make necessary changes to have a personalized website. The following is a list of the places I recommend checking for the latter:


### menus.yaml: {#menus-dot-yaml}

This file contains configuration information of the menu bar. The \`main\` entry contains the sections to be included in it with three parameters:

-   name: This is the name the menu will display in the menu bar.
-   url: You can specify any website address. Conveniently, this theme allows to user to use '#&lt;widget&gt;' where &lt;widget&gt; can be any section in your content directory.
-   weight: This number specifies the order of apparence for each menu. Assuming each entry has unique weight, entry A appears to the left of entry B if and only if the weght of entry A is smaller than the weight of entry B, i.e. entries with smaller weight appear first to the left.


#### Location {#location}

```bash
$WEBSITE_PATH/config/_default/menus.yaml
```


### params.yaml: {#params-dot-yaml}

This file contains parameters like the color scheme to be used, google analytics, \\(\LaTeX\\) support, etc.


#### Location {#location}

```bash
$WEBSITE_PATH/config/_default/params.yaml
```


#### Additional settings {#additional-settings}

I recommend to explore this section to enable/disable any options you might be interested. Nonetheless, I think you should change the footer parameter, especifically the copyright entry which initially contains '... {year} Me ...'. Of course the latter should be changed to your name.


### config.yaml: {#config-dot-yaml}

This file contains important entries like 'title' and 'baseURL'. The information in the 'title' entry will be used as a 'home buttom'. Additionally, make sure to setup your 'baseURL' with a trailing slash before making a deploy with the command

```bash
hugo
```


#### Location {#location}

```bash
$WEBSITE_PATH/config/_default/config.yaml
```


#### Additional settings {#additional-settings}

I'd recommend to set to true the property

```bash
canonifyURLS: true
```

Otherwise, I noticed the button with the name of the website has a link to the parent directory in your host domain.


## Workflow {#workflow}


### Adding publications {#adding-publications}

As mentioned before, I noticed two mechanisms to add publications into your academic themed website according to the official [documentation.](https://wowchemy.com/docs/content/publications/) The default directory for making changes about is `$WEBSITE_PATH/content/publication`. In my case, I decided to change a bit the format and rearrange the structure a little bit. In any case, the following should be useful whether you continue using the default settings or decide to make changes.


#### Manually {#manually}

For each publication, it requires a named directory, say `A`, inside `$WEBSITE_PATH/content/publication/`

The content for `$WEBSITE_PATH/content/publication/A/` should contain the following:

-   cite.bib: Basically it contains the information for your publications to be added into a bibtex library.
-   index.md: The most relevant entries for this file includes title and authors.

If you would like to include a pdf of your publication then it's necessary to include it inside the directory with the same name of such directory. In our example this would be `$WEBSITE_PATH/content/publication/A/A.pdf`


#### Using the python package academic {#using-the-python-package-academic}

You can install it with the following command:

```bash
pip3 install -U academic
```

If you have a bibtex file with bib entries of your publications, say `./data/publications.bib`, you only need to execute the following command to automatically create publication entries in your website:

```bash
academic import --bibtex data/publications.bib
```


### Creating a post {#creating-a-post}


#### Manually {#manually}

The following are steps to add posts using mardown files:

-   Create a markdown file inside the directory `.content/posts/`
-   The header of such file should be of the form:
    ```markdown
    +++
    title = "My first post: how to make posts and academic websites using Hugo with the academic theme"
    author = ["Jose Abel Castellanos Joo"]
    date = 2022-08-13
    draft = false
    +++
    <content-goes-here>
    ```


#### Using Ox-hugo {#using-ox-hugo}

I personally use this approach since I have already setup many [yasnippets](https://github.com/joaotavora/yasnippet) for org-mode and the ox-hugo was easy to install. This workflow uses a single org file (recommended by the author of the package) which contains first level headers associated to some section of your website, and each second level header will be translated as a markdown file in your project.

It's recommend to have this single file in a separate directory from the hugo original structure, say `./content-org`. The header of this single file should be

```org
#+hugo_base_dir: ../
#+author: <your-name>
```

The relevant properties for ox hugo is the `:EXPORT_HUGO_SECTION:` which should match the directory where the transpiled markdown file will be store. In my case for my Posts section the latter is the following:

```org
* Posts
:PROPERTIES:
:EXPORT_HUGO_SECTION: posts
:END:
```


### Suggested Makefile to automate several tasks {#suggested-makefile-to-automate-several-tasks}

The following is my Makefile I use to automate some building constructions. Additionally, it contains other scripts to change settings like the baseURL and icons.

```makefile
USERNAME='jose.castellanosjoo'
DOMAIN='cs.unm.edu'
BASE_URL='https:\/\/www.$(DOMAIN)\/~$(USERNAME)\/'
CURRENT_ICON_PATH=~/Pictures/icon.png
UNAME_S := $(shell uname -s)
ifeq ($(UNAME_S),Darwin)
	BROWSER=/Applications/Firefox.app/Contents/MacOS/firefox-bin
endif
ifeq ($(UNAME_S),Linux)
	BROWSER=firefox
endif

.PHONY: build test clean deploy setBaseUrl setLogo

build:
	hugo -D

test:
	hugo server -D &
	$(BROWSER) --new-tab http://localhost:1313/~$(USERNAME)/

clean:
	@rm -rf public

deploy:
	@echo 'Make sure BASE_URL is correct.'
	rsync -avz --delete public/ $(USERNAME)@moons.$(DOMAIN):~/public_html

setBaseUrl:
	sed -i "s/baseURL:.*/baseURL: $(BASE_URL)/g" ./config/_default/config.yaml

setLogo:
	@cp $(CURRENT_ICON_PATH) ./assets/media/icon.png

updatePublications:
	academic --overwrite import --bibtex ./static/CV/publications.bib
```