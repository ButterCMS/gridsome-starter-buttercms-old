<template>
  <Layout>
    <h1>Blog</h1>
    <!-- List posts -->
    <div class="posts">
      <PostCard
        v-for="edge in $page.posts.edges"
        :key="edge.node.id"
        :post="edge.node"
      />
    </div>
  </Layout>
</template>

<page-query>
query {
  posts: allButterPosts(order: ASC) {
    edges {
      node {
        id
        title
        url
        published  (format: "MMMM Do, YYYY")
        slug
        summary
        body
        featured_image
        tags {
          name
          slug
        }
        categories {
          name
          slug
        }
        author {
          first_name
          last_name
        }
      }
    }
  }
}
</page-query>

<script>
import PostCard from "~/components/PostCard.vue";

export default {
  components: {
    PostCard
  },
  metaInfo: {
    title: "Hello, ButterCMS!"
  }
};
</script>

<style></style>
