<template>
  <div class="content">
    <ShowrealCard class="max-width-block showreal-main" @down="scrollDown()"/>
    <ServiceCardList class="margin-top-block max-width-block" ref="service"/>
    <VideoCardLast class="margin-top-block max-width-block" />
    <AboutUsCard class="margin-top-block max-width-block"/>
    <ReviewCardLast class="margin-top-block"/>
    <FeedbackCard id="feedback" class="margin-top-block margin-bottom-block max-width-block"/>
  </div>
</template>

<style lang="scss">
.showreal-main {
  border-radius: 0px 0px 15px 15px;
}
</style>

<script>
export default {
  methods: {
    scrollDown () {
      this.$refs.service.$el.scrollIntoView({ behavior: "smooth" });
    }
  }
}
</script>
