<template>
<div class="review-container">
  <div class="review-author-container">
    <img :src="avatar.link" alt="" class="review-avatar">
    <div class="review-author-info-container">
      <span class="review-author">{{author}}</span>
      <a :href="postLink" class="review-post-link">оригинал поста</a>
    </div>
  </div>
  <p class="review-text">{{text}}</p>
  <VideoCard v-if="isViewVideo()"
  :img="videoPreviewImg"
  :video="videoPreviewVideo"
  :title="video.title"
  :time="video.time"
  @click="linkPush()" />
</div>
</template>

<style lang="scss">
.review-container {
  max-width: 1000px;
  display: flex;
  flex-direction: column;
  .review-author-container {
    display: flex;
    flex-direction: row;

    .review-author-info-container {
      display: flex;
      flex-direction: column;
      justify-content: center;

      margin-left: 16px;

      .review-author {
        @include text-font;
        font-weight: 500;
        color: $text-black-color;
      }

      .review-post-link{
        @include text-font;
        color: $text-black-lighter-color;

        transition: all .2s linear;
        &:hover{
          color: $text-black-color;
        }
        &:active{
          color: $text-black-light-color;
        }
      }
    }

    .review-avatar{
      border-radius: 100px;
      width: 96px;
      height: 96px;
    }
  }

  .review-text {
      @include text-font;
      line-height: 150%;
      padding: 10px 0px;
    }
}
</style>

<script>
export default {
  props: {
    reviewLink: { type: String, required: true },
    author: { type: String, required: true },
    avatar: { type: Object, required: true },
    postLink:{ type: String, required: true },
    text:{ type: String, required: true },
    video: { type: Object }
  },
  computed: {
    videoPreviewImg () {
      if (typeof this.video != 'undefined') return this.video.previewImg
    },
    videoPreviewVideo () {
      if (typeof this.video != 'undefined') return this.video.previewVideo
    }
  },
  methods: {
    isViewVideo (){
      return typeof this.video != 'undefined'
    },
    linkPush (){
      if (typeof this.video !== 'undefined')
      {
        if (typeof this.video.link !== 'undefined' && this.video.link !== "")
          var link = this.video.link;
          console.log(link);
          this.$router.push(link)
      }

    }
  }
}
</script>
