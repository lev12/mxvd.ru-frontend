<template>
  <div class="video-card" @click="clickOnVideoCard()">
    <div class="video-preview-container">
      <img :src=img alt="" class="video-preview-img">
      <video :src=video class="video-preview-video" autoplay loop muted></video>
      <div v-if="!compact" class="video-duration">
        <span>{{time}}</span>
      </div>
    </div>
    <h3 v-if="!compact" class="video-card-title">{{title}}</h3>
  </div>
</template>

<style lang="scss">
.video-card {
  display: flex;
  flex-direction: column;
}

.video-card-title{
  @include text-large-font;
  margin-top: 12px;
  margin-left: 20px;
  margin-bottom: 10px;
}

.video-preview-container{
  position: relative;
  border-radius: 15px;
  overflow: hidden;
  display: flex;

  .video-duration{
    @include text-small-font;

    position: absolute;
    color: white;
    background-color: rgba($color: #000000, $alpha: 0.1);
    right: 15px;
    bottom: 15px;

    z-index: 2;

    padding: 4px 8px;
    border-radius: 10px;
  }

  .video-preview-img{
    position: absolute;
    width: 100%;
    z-index: 1;

    transition: 0.3s;
    &:hover{
      opacity: 0;
    }
  }

  .video-preview-video{
    position: relative;
    width: 100%;
    object-fit: cover;
    z-index: 0;
  }


}

</style>

<script  >
export default{
  props: {
    title: {
      type: String,
      required: false,
      default: "Название"
    },
    time: {
      type: String,
      required: false,
      default: "00:00"
    },
    img: {
      type: String,
      required: true,
      default: "https://mxvd.ru/files/portfolio/img/Shipyard_preview.jpg"
    },
    video: {
      type: String,
      required: true,
      default: "https://mxvd.ru/files/portfolio/video/Shipyard_preview.mp4"
    },
    compact: {
      type: Boolean,
      required: false,
      default: false
    }
  },
  methods: {
    clickOnVideoCard() {
      this.$emit('click')
    }
  }

}


</script>
