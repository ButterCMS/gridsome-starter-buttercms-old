<template>
  <div class="post-meta">
    <span>Posted {{ post.published }}</span>
    <span v-if="post.author">
      by {{ post.author.first_name }} {{ post.author.last_name }}</span
    >
  </div>
</template>

<script>
export default {
  props: ["post"],
};
</script>

<style>
.post-meta {
  font-size: 0.8em;
  opacity: 0.8;
}
</style>
