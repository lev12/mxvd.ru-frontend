<template>
<div class="review-card-container">
  <div class="review-card-author-container">
    <img :src="avatar.link" alt="" class="review-card-avatar">
    <div class="review-card-author-info-container">
      <span class="review-card-author">{{author}}</span>
      <a :href="postLink" class="review-card-post-link">{{titlePostLink}}</a>
    </div>
  </div>
  <p class="review-card-text">{{reviewText}}&nbsp<a v-if="readMore" href="" class="review-card-read-more">{{titleReadMore}}</a></p>
  <VideoCard v-if="isViewVideo()" compact
  :img="videoPreviewImg"
  :video="videoPreviewVideo"
  @click="linkPush()" />
</div>
</template>

<style lang="scss">
.review-card-container {
  width: 472px;
  .review-card-author-container {
    display: flex;
    flex-direction: row;

    .review-card-author-info-container {
      display: flex;
      flex-direction: column;
      justify-content: center;

      margin-left: 16px;

      .review-card-author {
        @include text-font;
        font-weight: 500;
        color: $text-black-color;
      }

      .review-card-post-link{
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

    .review-card-avatar{
      border-radius: 100px;
      width: 96px;
      height: 96px;
    }
  }

  .review-card-text {
      @include text-font;
      line-height: 150%;

      padding: 10px 0px;

      height: 64px;
      overflow: hidden;
    }
}
</style>

<script >
export default {
  props: {
    reviewLink: { type: String, required: true },
    author: { type: String, required: true },
    avatar: { type: Object, required: true },
    postLink:{ type: String, required: true },
    text:{ type: String, required: true },
    video: { type: Object }
  },
  data() {
    return {
      titlePostLink: "оригинал поста",
      titleReadMore: "читать дальше",
      readMore: false,
      maxText: 108
    }
  },
  computed: {
    reviewText () {
      if (this.text.length > this.maxText)
      {
        this.readMore = true;
        return this.text.substring(0, this.maxText) + "...";
      }
      else return this.text;
    },
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
          this.$router.push("/work/" + link)
      }

    }
  }
}
</script>
