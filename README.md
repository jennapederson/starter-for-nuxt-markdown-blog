# starter-for-nuxt-markdown-blog

> Starter for a Nuxt Markdown Blog

Check it out here: https://starter-for-nuxt-markdown-blog.netlify.com/

## Build Setup

``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# run via netlify CLI with functions
$ netlify dev

When running via `netflify dev` point your browser at localhost:8888 so the site and functions are hosted on the same port.

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

## Functions

### Running the send-contact-email function

$ netlify functions:invoke send-contact-email --no-identity --payload '{"contactEmail" : "jenna@example.com", "contactName" : "Jenna", "message" : "Hello world from a function!"}'

# Deploy Your Own On Netlify

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/jennapederson/starter-for-nuxt-markdown-blog)