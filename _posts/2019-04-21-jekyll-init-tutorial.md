# Static Blog with GitHub Pages and Jekyll

GitHub pages allows you to turn github repositories into static websites which can be used to showcase portfolios, projects, documentations and many more.  It is an excellent alternative to payed hosting solutions and it is very easy to setup. Although GitHub provides an excellent and free hosting solution, it can be hard to build beautiful professional websites and blogs with lots of context.  Jekyll is a tool for transforming markdown text into static websites, no databases needed. In this simple tutorial we will setup an empty Jekyll site and host it on GitHub. First make a new empty project on GitHub named **blog**. Make sure the project is public and that it **does not** have a *Readme* file. 

## Setup

After that open a desired location on your PC and make a new Jekyll project called **blog** using the command:

```bash
jekyll new blog
```

To run the Jekyll site on the local server  you can type:

```bash
cd blog
bundle exec jekyll serve
```

The website will be available at "http://localhost:4000". This server is excellent for the development and for quick testing of the website. 

Go into the newly created folder and open **_config.yml** file in your favorite editor. Find the **baseurl** line and edit it:

```bash
cd blog
xed _config.yml
```

```yaml
baseurl: "/blog" # the subpath of your site, e.g. /blog
```

Open the file **Gemfile** in your favorite editor.

```bash
xed Gemfile
```

If the file is empty add the following lines:

```ruby
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
```

After that use git to initialize the folder and create a `gh-pages` branch.

```bash
git init
```

GitHub pages can publish site's source files from the `master` or the`gh-pages` branch. If the repository doesn't have any of these branches, the publishing source will be set to **None** and the site will not be published. In this tutorial we will use the `gh-pages` branch.

```bash
git checkout -b gh-pages
```

Use git to add all files and commit the changes. 

```bash
git add .
git commit -m "first commit"
```

Finally we will connect our local git repository to the repository on GitHub and push the changes.

```bash
git remote add origin https://github.com/username/blog
git push origin gh-pages
```



