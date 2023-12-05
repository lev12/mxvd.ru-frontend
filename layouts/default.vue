<template>
  <div>
    <HeaderMain @clickFeedback="feedbackView()"/>
    <div class="wrapper">
      <Nuxt />
    </div>
    <FooterMain />
  </div>
</template>

<style lang="scss">
.wrapper{
  min-height: calc(100vh - $header-height - $footer-height);
}
</style>

<script>
export default {
  methods: {
    feedbackView() {
      let element = this.$el.querySelector("#feedback");
      if (element == null)
      {

      }
      else
      {
        element.scrollIntoView({ behavior: "smooth" })
      }
    }
  }
}
</script>
