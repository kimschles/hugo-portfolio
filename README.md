# Kim's Hugo Portfolio 

This is the project that generates the code for [kimschlesinger.com](https://kimschlesinger.com/). It is built with [Hugo](https://gohugo.io/) and deployed with [Netlify](https://www.netlify.com/). 

## Prerequisites

  - go 1.14+
  - hugo v0.71.0+ 
  - a github account 
  - a netlify account 

## Working on the Project 

Clone this repo, change into the directory and run `hugo serve -D`. Open your browser to `localhost:1313` to see the site. Changes you make are picked up by the server and shown automatically. 

I wanted to customize the Pixyll theme more than is possible through the `config.toml` file, so I forked the theme and used git submodule to link to [that repo](https://github.com/kimschles/hugo-theme-pixyll). I got this idea from [this blog post](https://www.andrewhoog.com/post/git-submodule-for-hugo-themes/) by Andrew Hoog. 

If you're actually looking to build your own portfolio with Hugo, I recommend the [Quick Start Tutorial](https://gohugo.io/getting-started/quick-start/). 

## Deployment

This project is deployed with Netlify. The `netlify.toml` file lives at the root of this directory. You'll also need to use your github account to sign in to Netlify, create a new project and link with the github repo.


