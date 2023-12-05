<template>
<div class="video-other-container">
  <h2 class="video-other-title">{{title}}</h2>
  <VideoCardGrid :columnCount="3" :rowCount="1" :videoSet="video" />
</div>
</template>

<style lang="scss">
.video-other-container {
  display: flex;
  flex-direction: column;
  justify-content: center;

  .video-other-title {
    @include h3-font;
    margin-bottom: 10px;
    font-weight: 300;
  }
}
</style>

<script>
export default {
  props: {
    title: {
      type: String,
      required: false,
      default: "Другие работы"
    },
    video: {
      type: Array,
      required: true
    }
  }
}
</script>
