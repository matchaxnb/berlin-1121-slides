+++
weight = 40

+++
{{<slide template="devops_ws">}}
# Workshop

# Build Your Own Website

---
{{<slide template="devops_ws">}}
# Workshop

## We're all gonna create an open source personal website

## We will build it with [Hugo](https://gohugo.io/), a static website generator

## We will host it on [GitHub Pages](https://pages.github.com/) for free

## We will automate it all with [GitHub Actions](https://github.com/features/actions) for free

### For the contents, I propose a [selection of poems](https://tinyurl.com/poems-b2021).

---
{{<slide template="devops_ws">}}
# Workshop

# Get your computers

If you don't have one or you don't feel like going through all the steps, the instructions will be available online so you can do it from home.

---
{{<slide template="devops_ws">}}
# Workshop

# Let's download tools

Please download Hugo from [https://gohugo.io](https://gohugo.io)
{{<figure src="gohugoqr.png" height="200">}}

Please install Git on your computer if that's not done.

Optionally, install GitHub Desktop from [https://desktop.github.com/](https://desktop.github.com/).

---
{{<slide template="devops_ws">}}
## Create a GitHub repository for your website

Connect to GitHub.com and just do that!

The repository needs to be named `<YourUsername>.github.io` for GitHub Pages to work.
{{<figure src="new-repo.png" height="200">}}

---
{{<slide template="devops_ws">}}
# If you don't have a GitHub account

Create one for free *and download GitHub Desktop and VS Code*.


---
{{<slide template="devops_ws">}}
# Create a local repository

Using GitHub Desktop, it's very straightforward

Using the CLI it's something like

```bash
git init yourusername.github.io --initial-branch=main
cd yourusername.github.io
git remote add origin git@github.com:yourusername/yourusername.github.io
```

---
{{<slide template="devops_ws">}}
# Bootstrapping Hugo

## Open the newly created folder in your IDE.
## Open a terminal in that directory (VS Code: right click -> open in integrated terminal)
## Run this simple command
```bash
hugo new site . --force
```

---
{{<slide template="devops_ws">}}
# Install a Hugo theme (skin)

We will install the Diary theme

{{<figure src="diary-hugo.png" height="300">}}

---
{{<slide template="devops_ws">}}
# Install the Diary theme
## In the terminal, run the following command
```bash
git submodule add https://github.com/AmazingRise/hugo-theme-diary.git themes/diary
```

## Tweak the config.toml file

It will look like

```toml
baseURL = 'https://yourusername.github.io/'
languageCode = 'en-uk'
title = "My Poetry blog"

theme = 'diary'
```

---
{{<slide template="devops_ws">}}
# Let's see how it looks

In the same terminal, run

```bash
hugo server -D
```

and open the given link in your web browser. Check it out!


---
{{<slide template="devops_ws">}}
# Publish the code

Let's publish the code by committing it and pushing it

## Committing

Commiting is writing to the Git history your changes with an explanatory message. Using the terminal, that's a matter of doing

```bash
git add .
git commit -m "first commit for my website"
```

With GitHub Desktop, it's still very straightforward: add all files, and commit them.

---
{{<slide template="devops_ws">}}
# Publish the code
## Pushing

Pushing commits means publishing them to a remote location. Here, we're talking about GitHub.

With GitHub Desktop, just click the Push button.

With the CLI, it's 

```bash
git push -u origin main
```

The source code to your website is now online! Check it out on your browser.

---
{{<slide template="devops_ws">}}
# Publishing the website in its true form

We will add a GitHub Action for Hugo. This will do all the heavy lifting for us.

- Create a folder in your repository .github/workflows/
- Get it from [https://tinyurl.com/berlin-hugo](https://tinyurl.com/berlin-hugo).
- Save this file to .github/workflows/gh-pages.yml
- Commit, push

See the magic happen in the Actions tab of your repository on GitHub.

---
{{<slide template="devops_ws">}}
# Actually seeing the website

Since we are doing the GitHub Action for the first time, we need to turn on the GitHub Pages feature.

- Go to your repository's Settings tab on GitHub
- Click the Pages tab on the left menu
- Pick the Source for GitHub Pages as branch gh-pages and click Save.
- That's it! Your website will appear online after a few seconds on `https://<YourUsername>.github.io`


---
{{<slide template="devops_ws">}}
# Adding contents

## An about me page

From the terminal:

```bash
hugo new about-me/index.md
```

Remove the `draft: true` mention and just type your blog in markdown.

Commit, push, see it online!

---
{{<slide template="devops_ws">}}
# Adding moar contents
## Queer and feminist poems

- Create a `contents/posts` folder in your repository
- Pick some from [https://tinyurl.com/poems-b2021](https://tinyurl.com/poems-b2021).
- Save them (raw form) under the newly created folder.
- Commit, push, see it online.

---
{{<slide template="devops_ws">}}
# Going further

Connect with your peers, star their GitHub repository, then maybe add a link to their website in your repository and open a pull request so they add yours. A lot of things happen in the DevOps world through cooperation, keep that in mind.

DevOps takes its roots into the Agile movement, and Agile people are fond of Open Source in general. The entire ecosystem is shaped by it.
