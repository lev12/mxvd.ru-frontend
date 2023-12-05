<template>
<div class="service-container" :id="id">
  <ShowrealCard class="service-showreal"
                :title="title" :description="description" :showrealSrc="showrealSrc"
                :buttons="actionButtons" :showArrowDown="blocks != null" @down="scrollDown()" :h1Title="false"/>
  <div ref="serviceBlocks" v-if="blocks != null"  class="service-blocks-container">
    <ServiceBlock v-for="(block, index) in blocks"
                  :title="block.title" :description="block.description" :image="block.image"
                  :flip="index % 2 === 0"/>
  </div>
  <div class="service-video-container" v-if="videos != null">
    <VideoCardGrid :videoSet="videos" :columnCount="3" :rowCount="1"/>
    <ButtonMain class="service-video-button" v-if="videoMoreLink != null" label="Больше работ" color="white" @click="videoMoreAction()" />
  </div>
</div>
</template>

<style lang="scss">
.service-container {
  display: flex;
  flex-direction: column;
  .service-showreal {
    margin-bottom: 30px;
  }

  .service-blocks-container {
    display: flex;
    flex-direction: column;

    :not(:first-child) {
      margin-top: 30px;
    }
  }

  .service-video-container {
    display: flex;
    flex-direction: column;
    align-items: center;

    margin-top: 50px;
  }

  .service-video-button {
    width: 285px;
    height: 34px;
  }
}
</style>

<script>
export default {
  data() {
    return {

    }
  },
  props: {
    id: {
      type: String,
      require: true
    },
    title: {
      type: String,
      require: true
    },
    description: {
      type: String,
      require: false,
      default: ""
    },
    showrealSrc: {
      type: String,
      require: true
    },
    actionButtons: {
      type: Array,
      require: false
    },
    blocks: {
      type: Array,
      require: false,
      default: null
    },
    videos: {
      type: Array,
      require: false,
      default: null
    },
    videoMoreLink: {
      type: String,
      require: false,
      default: null
    }
  },
  methods: {
    videoMoreAction () {
      this.$router.push(this.videoMoreLink);
    },
    scrollDown(){
      this.$refs.serviceBlocks.scrollIntoView({ behavior: "smooth" })
    }
  }
}
</script>
