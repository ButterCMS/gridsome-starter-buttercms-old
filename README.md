# Gridsome ButterCMS Starter

- Demo: [https://buttercms-gridsome-starter.netlify.app/](https://buttercms-gridsome-starter.netlify.app/)

### 1. cd into the project and install dependencies

```
cd gridsome-starter-buttercms
npm install
```

### 2. Setup a ButterCMS account

1. Create a free account on ButterCMS - https://buttercms.com/.
2. Copy and save off your AuthToken from the welcome screen or Profile >> settings (it looks like this: a985f3f782f2005...)
3. Create and publish a new `customer_case_study` page type in your ButterCMS account by following simple steps https://buttercms.com/docs/api-client/gridsome#PagesPageType

### 3. In gridsome.config.js, replace the test Auth token (0126997a0f359dffdf0a4200b9c229161c7610ec) with the Auth token from your ButterCMS account

```
module.exports = {
  siteName: 'Gridsome',
  plugins: [
    {
      use: 'gridsome-source-buttercms',
      options: {
        authToken: '56655b6ca9edd2b2fd0c8b6e51148cfb119987db', // change to your own auth token
        collections: [''],
        pages: '',
        pageTypes: 'customer_case_study'
      }
    }
  ]
}
```

### 4. Run the project locally on port `8080`

`npm run develop`

# Learn more

ButterCMS can be used as a [gridsome cms](https://buttercms.com/gridsome-cms/) and [gridsome blog engine](https://buttercms.com/gridsome-blog-engine/). This starter project demonstrates how to use Butter with Gridsome.
