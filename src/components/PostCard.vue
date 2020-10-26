<template>
  <div class="post-card__content-box">
    <g-link class="post-card__header" :to="`blog/${post.slug}`">
      <g-image
        alt="Cover image"
        v-if="post.featured_image"
        class="post-card__image"
        :src="post.featured_image"
      />
    </g-link>
    <div class="post-card__content">
      <h2 class="post-card__title">
        <g-link :to="`blog/${post.slug}`">{{post.title}}</g-link>
      </h2>
      <div>
        <small  class="post-card__category" v-for="category in post.categories" :key="category.slug">{{category.name}}</small>
      </div>
      <p class="post-card__description" v-html="post.summary" />
      <PostMeta class="post-card__meta" :post="post" />
    </div>
  </div>
</template>

<script>
import PostMeta from "~/components/PostMeta"

export default {
  components: {
    PostMeta,
  },
  props: ["post"],
}
</script>

<style lang="scss">
.post-card {
  margin-bottom: var(--space);
  position: relative;

  &__content-box {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    margin-bottom: 20px;
  }

  &__header {
    margin-left: calc(var(--space) * -1);
    margin-right: calc(var(--space) * -1);
    margin-bottom: calc(var(--space) / 2);
    margin-top: calc(var(--space) * -1);
    overflow: hidden;
    border-radius: var(--radius) var(--radius) 0 0;
    flex-basis: 25%;
    &:empty {
      display: none;
    }
  }
  &__content {
    flex-basis: 75%;
    box-sizing: border-box;
    padding: 0 10px;
  }
  &__image {
    width: 100%;
  }
  &__title {
    margin-top: 0;
    margin-bottom: 0;
  }

  &__description {
    margin-top: 0;
    display: block;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
  }

  &__tags {
    z-index: 1;
    position: relative;
  }

  &__link {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    overflow: hidden;
    text-indent: -9999px;
    z-index: 0;
  }
  
  &__category {
    margin-right: 5px
  }
}
</style>
