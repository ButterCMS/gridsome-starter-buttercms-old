<template>
  <div class=''>
    <g-image
        alt="Cover image"
        v-if="about.data.author_image"
        class="about__image g-image"
        :src="about.data.author_image"
      />
    <h1 class="study__title" v-html="about.data.first_last" />
    <h3 class="study__title" v-html="about.data.tagline" />
    <p class="study__description" v-html="about.data.body_text1" />
    <p class="study__description" v-html="about.data.body_text2" />
    <p class="study__description" v-html="about.data.body_text3" />
  </div>
</template>

<script>
export default {
  components: {},
  props: ["about"]
};
</script>

<style lang="scss">
.about {
  margin-bottom: var(--space);
  position: relative;

  &__content-box {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
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
  }
  &__image {
    border: 2px solid gray;
    width: 20%;
    margin-left: 20px;
    margin-right: auto;
    box-shadow: 1px 10px 30px 0 rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
    padding: 5px;
    align-content: center;
  }
  &__title {
    margin-top: 0;
    margin-bottom: 0;
  }

  &__description {
    margin-top: 0;
    display: block;
    margin-bottom: 20px;
    margin-block-start: 0em;
    margin-block-end: 1rem;
    margin-inline-start: 0px;
    margin-inline-end: 1rem;
  }

  &:hover {
    transform: translateY(-5px);
    box-shadow: 1px 10px 30px 0 rgba(0, 0, 0, 0.1);
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
}
</style>
