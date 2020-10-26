<template>
  <div class="post-meta">Posted {{ post.published }} by {{post.author.first_name}} {{post.author.last_name}}</div>
</template>

<script>
export default {
  props: ["post"]
};
</script>

<style>
.post-meta {
  font-size: 0.8em;
  opacity: 0.8;
}
</style>
