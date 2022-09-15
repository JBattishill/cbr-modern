# cbr-modern

This repo contains the bare-minimum you need to get started twith Vue/Nuxt.

You will see that I load the buildings and content from the home page.

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Reflection

I chose to keep my site as basic and functional as possible to allow myself time to work on understanding APIs and making the website as dynamic as possible.

I was not able to get the website hosted using the the examples provided however I am determined to have this resolved in time for the next assignment.

## Goals

• A simple, clean website that's easy to navigate and understand
• Dynamic, pulling data from API to display page data and images etc.
• Responsive and still functional on smaller devices

## Inspiration

I honestly didn't take much inspiration from anywhere except the template and code provided by Ben :)

I used the template in conjuction with animation examples from CSS-Tricks. Everything else I wrote myself.

## Production Process
I started with focusing on splitting up the data from the events page, it was far too much on a single view. With Ben's help, I was able to get the view functional and displaying data correctly using NuxtJS's v-html function.

### Lessons learned
NuxtJS is very complex and difficult to pick up... but eventually things made sense and things started to come together.

This was first project using Bootstrap, I don't think I really picked it up properly but that wasn't what I was really focused on for this project.

Overall I am pretty happy with how it turned out and I am find myself thinking forward to the next assignment and conceptualising ideas. But i need to stop, I havent slept properly in like 4 days so I can relax this weekend...

Thanks

Jarryd Eastwood (formerly Battishill)
u3092157

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).

### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).

## Node version

nvm install v16.15.0

