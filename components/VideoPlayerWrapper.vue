<template>
<div class="video-player-wrapper-container">
  <iframe class="v" v-if="video.typeSrc === 'youtube'" :src="video.data" width="560" height="315" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>
</template>

<style lang="scss">
.video-player-wrapper-container {
  position: relative;
    width: 100%;
    height: 56.25vw;
    max-height: 810px;
    border-radius: 10px;
    overflow: hidden;
}
.v{
  position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>

<script>
export default {
props: {
  video: {
    type: Object,
    required: true
  }
}
}
</script>
