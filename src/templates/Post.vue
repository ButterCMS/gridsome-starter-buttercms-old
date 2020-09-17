<template>
  <Layout>
    <div class="post-title">
      <h1 class="post-title__text">{{ $page.post.edges[0].node.title }}</h1>

      <div class="post-meta">Posted on {{ $page.post.edges[0].node.published }}</div>
    </div>

    <div class="post content-box">
      <div class="post__header">
        <g-image
          alt="Featured image"
          v-if="$page.post.edges[0].node.featured_image"
          :src="$page.post.edges[0].node.featured_image"
        />
      </div>

      <div class="post__content" v-html="$page.post.edges[0].node.body" />

      <div class="post__footer">
        <PostTags :post="$page.post.edges[0].node.post" />
      </div>
    </div>

    <div class="post-comments">
      <!-- Add comment widgets here -->
    </div>
  </Layout>
</template>

<script>
import PostMeta from "~/components/PostMeta"

export default {
  components: {
    PostMeta,
  },
  metaInfo() {
    return {
      title: this.$page.post.edges[0].node.title,
      meta: [
        {
          name: "summary",
          content: this.$page.post.edges[0].node.summary,
        },
      ],
    }
  },
}
</script>

<page-query>
query postQuery ($slug: String!) {
  post: allButterPosts(filter: { slug: { eq: $slug } }) {
      edges {
        node {
          id
          body
          featured_image
          summary
          published  (format: "MMMM Do, YYYY")
          title
          slug
        }
      }
    }
}
</page-query>

<style>
.post-title {
  padding: calc(var(--space) / 2) 0 calc(var(--space) / 2);
  text-align: center;
}

.post {
  &__header {
    width: calc(100% + var(--space) * 2);
    margin-left: calc(var(--space) * -1);
    margin-top: calc(var(--space) * -1);
    margin-bottom: calc(var(--space) / 2);
    overflow: hidden;
    border-radius: var(--radius) var(--radius) 0 0;

    img {
      width: 100%;
    }

    &:empty {
      display: none;
    }
  }

  &__content {
    h2:first-child {
      margin-top: 0;
    }

    p:first-of-type {
      font-size: 1.2em;
      color: var(--title-color);
    }

    img {
      width: calc(100% + var(--space) * 2);
      margin-left: calc(var(--space) * -1);
      display: block;
      max-width: none;
    }
  }
}

.post-comments {
  padding: calc(var(--space) / 2);

  &:empty {
    display: none;
  }
}

.post-author {
  margin-top: calc(var(--space) / 2);
}

img {
  max-width: 100% !important;
  height: auto !important;
}
</style>
