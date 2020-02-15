<template>
  <Layout>
    <h1>About the Author</h1>
      <AnAbout 
          v-for="edge in $page.abouts.edges"
          :key="edge.node.id"
          :about="edge.node"
          />




      
  </Layout>
</template>


<page-query>
query {
  abouts: allButterPages{
    edges {
      node {
        data {
          first_last
          tagline
          body_text1
          body_text2
          body_text3
          author_image
        }
      }
    }
  }
}
</page-query>

<script>
import AnAbout from "~/components/AnAbout.vue";

export default {
  components: {
    AnAbout
  },
  metaInfo: {
    title: "Hello, ButterCMS!"
  }
};
</script>
