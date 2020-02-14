# Default starter for Gridsome

This is the project you get when you run `gridsome create new-project`.

### 1. Install/Update Gridsome CLI tool

`npm install --global @gridsome/cli`

### 2. Create a Gridsome project

1. `gridsome create my-gridsome-site` to install default starter
2. `cd my-gridsome-site` to open the folder
3. `gridsome develop` to start a local dev server at `http://localhost:8080`
4. Happy coding 🎉🙌

### 3. Taking the default Gridsome project to ButterCMS

1. Prepare to create a Gridsome project:
   `npm install --global @gridsome/cli` to update/install the gridsome CLI.
   `gridsome create <new_project_name>` to create your Gridsome project.
   CD into the project and `npm install gridsome-source-buttercms` to install the ButterCMS gridsome npm module.
   Let’s also include the npm modules for handling SCSS styling: `npm install -D sass-loader node-sass`
2. Create a free account on ButterCMS.
3. Copy and save off your AuthToken from the welcome screen or Profile >> settings (it looks like this: a985f3f782f2005...)
4. Add a second Blog Post to your ButterCMS account by going to Blog Posts, then click the green “Write New Post” button at the top and write and Publish your post.
5. Moving over to your project code, find your gridsome.config.js file and add to plugins:
   `{ use: "gridsome-source-buttercms", options: { authToken: 'a985f3f782f2005...,<your AuthToken>', collections: [''], pages: '', pageTypes: '' }`

6. Open `index.vue` in the pages folder (the default view) and make the changes described below in “Change pages/Index.vue”
7. Add a new vue component to the components folder, PostCard.vue, using the code below in “Add PostCard.vue” to components.
8. From your CLI, run `gridsome develop` and you should see two post summaries: the default ButterCMS post and your post.

# Learn more

ButterCMS can be used as a [gridsome cms](https://buttercms.com/gridsome-cms/) and [gridsome blog engine](https://buttercms.com/gridsome-blog-engine/). This starter project demonstrates how to use Butter with Gridsome.
