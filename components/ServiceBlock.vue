<template>
<div class="service-block-container">
  <div class="service-block-text-container">
    <h3 class="service-block-title">{{title}}</h3>
    <p class="service-block-description">{{description}}</p>
  </div>
  <img class="service-block-img" :src="image.src" :alt="image.alt">
</div>
</template>

<style lang="scss">
.service-block-container {
  display: flex;
  flex-direction: v-bind('flip ? "row" : "row-reverse"');
  justify-content: center;
  align-self: center;
  .service-block-text-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: v-bind('flip ? "left" : "right"');
    margin-right: v-bind('flip ? "100px" : "0px"');;
    margin-left: v-bind('flip ? "0px" : "100px"');;
  }

  .service-block-title {
    @include h2-font;
  }

  .service-block-description {
    @include text-font;
    max-width: 800px;
  }

  .service-block-img {
    height: 350px;
    width: 350px;
    border-radius: 100px;
  }
}
</style>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    image: {
      type: Object,
      required: true,
    },
    flip: {
      type: Boolean,
      required: false,
      default: false
    }
  }
}
</script>
