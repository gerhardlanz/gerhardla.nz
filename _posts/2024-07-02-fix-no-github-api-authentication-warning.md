---
layout: post
title:  "Fix “No Github API authentication” warning"
date: 2024-07-02
---

When building a Jekyll site locally, the following warning may be encountered in the terminal:

```bash
GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
```

When the [Github Pages gem ↗](https://rubygems.org/gems/github-pages) (`github-pages`) is included in the Gemfile, the [Jekyll Github Metadata gem ↗](https://rubygems.org/gems/jekyll-github-metadata) (`jekyll-github-metadata`) is automatically enabled for builds (including builds using this gem locally). The Jekyll Github Metadata gem pulls information from the GitHub API, but first [checks the environment for authentication ↗](https://github.com/jekyll/github-metadata/blob/8906f2b9c890f0aafef96423c7cd7e5047f7dae4/lib/jekyll-github-metadata/client.rb#L96-L97), which is required for some API calls. The "No GitHub API authentication could be found" warning is shown when no Github access token is found by the gem.

This is just a warning – and safe to ignore – but follow these steps to fix GitHub API authentication on macOS:

>Note: Instead of permanently adding the personal access token as a system variable, the token can temporarily be accessed by declaring it when building or serving the Jekyll site locally: `JEKYLL_GITHUB_TOKEN=<personal access token> bundle exec jekyll serve`

1. Create a Github [personal access token ↗](https://help.github.com/articles/creating-an-access-token-for-command-line-use/).

    a. In the upper-right corner of any page on GitHub, select the profile photo and navigate to *Settings > Developer settings > Personal access tokens > Fine-grained personal access tokens > Generate new token*.

    b. Provide a token name and expiration.

    c. Select *Repository access > Public Repositories (read-only)*.

    d. Select *Generate token*.

2. Open terminal and check the default shell.

    `echo $SHELL`

3. Open the corresponding shell file in your user directory (replace .zshrc with your default shell, e.g. .profile, .bashrc, .zshenv, .bash_profile).

    `open ~/.zshrc`

4. Add a new system variable referencing the personal access token.

    `export JEKYLL_GITHUB_TOKEN=<personal access token>`

5. In terminal run.

    `source ~/.zshrc`

6. Check the new system variable is accessible.

    `echo $JEKYLL_GITHUB_TOKEN`

7. In your Jekyll project, run.

    `bundle exec jekyll serve`
