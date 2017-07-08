# Real World React

> Real World React apps and their open source codebases for developers to learn from

Learn from React apps written by experienced developers.

You'll find the source code for the Real World React apps in the [`apps/`](apps/) subdirectory.

Thank you to every developer who has worked on a project this repo links to, your work is helping developers learn React.

## How to install on your computer

```bash
# Clone this git repo:
git clone git@github.com:jeromedalbert/real-world-react.git

cd real-world-react/

# The apps are linked to as git submodules.
# This will take some time...
git submodule update --init
```

## How you can analyze Real World React apps

Some of the examples below use [ag](https://github.com/ggreer/the_silver_searcher), but could just as well use grep or equivalent.

#### Global searches

```bash
# Simple search
ag -Q 'reduce(' --js

# What multi-line ternaries look like
ag -C '\?$' --js

# Cookie libraries people use
ag cookie -G 'package.json'
```

#### Compare a lot of files at once

```bash
# Find ideas on how to configure Webpack
# Opens all webpack.config files in your editor of choice (vim/subl/atom/etc)
vim $(find . -name '*webpack.config*')

# Output content from all package.json files
find . -name package.json | xargs cat
```

#### Find out how long eslintrc files usually are
```bash
find . -name '*eslintrc*' | xargs wc -l | sort
```

#### Compare the popularity of let vs const
```bash
ag 'let ' --js --stats-only | head -n 1
ag 'const ' --js --stats-only | head -n 1
```

## Information for Contributors

#### Is your app the right fit?

- A real world app should ideally be publicly accessible and used by real people in a production environment. As such, boilerplate, starter kits, libraries, and small demo/example projects are not really a good fit.
- Ideally most of the code should be frontend-oriented, in order to focus on React. Small backends may be OK, but should constitute the minority of the codebase.

That being said, don't hesitate to submit a pull request if you meet the criteria!

#### How to add a Real World App

Given a GitHub repo for an app `githubuser/foo`:

```bash
# Inside the project root:
git submodule add -b master git@github.com:githubuser/foo.git apps/foo
```

#### Updating the apps submodules to latest

The apps in `apps/` are git submodules. Git submodules are locked to a revision and don't stay in sync with the latest revision.

To update the revisions, run:

```bash
# This will take some time:
git submodule foreach git pull origin master
```

---

# Contributors

- Jerome Dalbert http://jeromedalbert.com
- Contributions are welcome, fork the GitHub repo, make your changes, then submit your pull request! Reach out if you'd like some help.
