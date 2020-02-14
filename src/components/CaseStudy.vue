<template>
  <div class="study__content-box">
    <div class="study__header">
      <g-image
        alt="Cover image"
        v-if="study.customer_logo"
        class="study__image"
        :src="study.customer_logo"
      />
    </div>
    <div class="study__content">
      <h3 class="study__title" v-html="study.data.headline" />
      <p class="study__description">(<span class="study__description" v-html="study.data.customer_industry" />
      / <span class="study__description" v-html="study.data.customer_subindustry" />)
      <p class="study__customer_attributes" v-html="study.data.customer_attributes" />
      </p>
      <g-image
        alt="Cover image"
        v-if="study.data.customer_logo"
        class="study__customer_logo"
        :src="study.data.customer_logo"
      />
      <hr/>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: ["study"]
};
</script>

<style lang="scss">
.study {
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
    flex-basis: 100%;
    &:empty {
      display: none;
    }
  }
  &__content {
    flex-basis: 100%;
  }
  &__customer_logo {
    border: 2px solid gray;
    width: 80%;
    margin-left: 20px;
    margin-right: auto;
    box-shadow: 1px 10px 30px 0 rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
    padding: 5px;
    align-content: center;
    margin-bottom: 20px;
  }
  &__title {
    margin-top: 0;
    margin-bottom: 0;
  }

  &__description {
    display: flex;
    margin-top: 0;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
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
