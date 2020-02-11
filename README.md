# Gridsome Starter Project

Sample starter project that uses the [ButterCMS Gridsome Source Plugin](https://github.com/ButterCMS/gridsome-source-buttercms) for pulling blog posts, authors, categories, tags, and content fields into [Gridsome](https://gridsome.org) from [ButterCMS](https://buttercms.com).

## Install

```
yarn add gridsome-source-buttercms

npm install gridsome-source-buttercms
```

## Usage

Add the plugin to your gridsome.config.js file

Configuration Example

```js
module.exports = {
  plugins: [
    {
      use: "gridsome-source-buttercms",
      options: {
      authToken: process.env.GRIDSOME_BUTTER_AUTHTOKEN ||process.env.BUTTER_AUTHTOKEN,
      // optional fields follows
      collections: [],
      pages: '',
      pageTypes: ''
      }
    }
  ]
}
```

# Learn more

ButterCMS can be used as a [gridsome cms](https://buttercms.com/gridsome-cms/) and [gridsome blog engine](https://buttercms.com/gridsome-blog-engine/). This starter project demonstrates how to use Butter with Gridsome.
