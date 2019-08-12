|Build Status|
|-----|
| [![Netlify Status](https://api.netlify.com/api/v1/badges/3d41d0d9-365a-42de-999d-56a7399f898f/deploy-status)](https://app.netlify.com/sites/cargurusblog/deploys) |

## Getting started

You need:

* `node 10+`
* `yarn 1.13.0`

Posts are written in markdown. You can use any markdown editor you like. [vscode's markdown all in one](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) plugin is very good for rich editing markdown files. 

(Unless you are one of the code owners of the blog, you may find it easier to fork a repository on Github and submit your pull requests from there.) 

## Authoring a new post

To author a new post run `yarn new:post "Your Post Name Here"` a directory, and markdown file will be created for you in `content/blog/Your-Post-Name-Here`

Then you can author the post as normal with markdown. To run the server locally, run `yarn install && yarn start`. If all is well you will will be able to see the blog at [http://localhost:8000/](http://localhost:8000/)

Our CI system checks for spelling errors, you can run this yourself with `yarn check:spell`, you will be prompted to either fix your mistakes or add your mistakes to a dictionary. You can add yourself to `authors/authors.json`, with some basic info about yourself, and a thumbnail can be placed in `content/assets/authors`.

## LaTeX

We use [Katex](https://katex.org/) as our math typesetting library. Katex has a [large table](https://katex.org/docs/supported.html) of supported functions, and [environments](https://katex.org/docs/supported.html#environments).

There are two modes to authoring equations `inline` and `display` 

Inline uses a single opening/closing `$` and will inline the function.

`$a^2 + b^2 = c^2$`

Display mode will center and block the equations, those are wrapped in opening/closing `$$` with a new line.

```
$$
a^2 + b^2 = c^2
$$
```




## Getting your post live

To get your post live, simply make a branch, create a pull request and then get it merged. Netlify will automatically pick up on new commits into master and deploy them. Any new content must be approved by @stodesca github will enforce this automatically with its codeowner system.


## Editing the code

To start the blog locally run `yarn install` and then run `yarn start`. The blog itself supports hot module reloading, so most changes you make should automatically apply in the browser. 

We use [less](http://lesscss.org/) as our css processor, and [css modules](https://github.com/css-modules/css-modules) to import our styles into our components. Each component should have a less file with the name of `component.module.less`. Note the `.module` for gatsby to understand a less file is a css module you have to have the `.module` otherwise your styles won't get imported.
