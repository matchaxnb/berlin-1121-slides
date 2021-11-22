# commands log for the hugo slides website

just quick notes about what was done here.

we follow this: https://gohugo.io/getting-started/quick-start/
and then we deploy to GitHub pages. GitLab would work the same (almost).

## create the directory with basic structure
```bash
hugo new site berlin-2021-slides
```
## git setup

Basically just setup the remote GitHub repository

```bash
git init
git remote add origin git@github.com:matchaxnb/berlin-1121-slides.git
git branch -M main
```

## theme selection

for this presentation, we use a reveal.js based theme. for the websites
we will use something else.

```bash
git submodule add git@github.com:dzello/reveal-hugo.git themes/reveal-hugo
```

this is a bit special because this is a slides theme. we use the
diary theme for the blog

```bash
git submodule add https://github.com/AmazingRise/hugo-theme-diary.git themes/diary
```

we want to use specific syntax because we're a geek so

```bash
git submodule add https://github.com/martignoni/hugo-notice.git themes/hugo-notice
```

and then we configure the config.toml for it (see how it is)

## trying stuff

```
hugo new posts/what-is-devops.md
# then edit stuff then...
hugo server -D
# and see the result
```
