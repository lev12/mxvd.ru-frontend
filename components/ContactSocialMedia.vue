<template>
<div class="contact-social-media">
  <h2 class="contact-social-media-title">Социальные сети</h2>
  <div class="contact-social-media-container">
    <a :href=item.link class="contact-social-media-link" v-for="item of media">
      <Icon :name=item.icon class="contact-social-media-icon"/>
    </a>
  </div>
</div>
</template>

<style lang="scss">
.contact-social-media {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .contact-social-media-title {
    @include h2-font;

    margin-bottom: 6px;
  }

  .contact-social-media-container {
    display: flex;
    flex-direction: row;
  }

  .contact-social-media-link:not(:first-child) {
    margin-left: 16px;
  }

  .contact-social-media-icon {
    height: 64px;
    width: 64px;
  }
}
</style>

<script>
export default {
  data () {
    return {
      media: [
        {
          icon: "vk-color",
          link: "https://vk.com/stdmaxvideo",
        },
        {
          icon: "youtube-color",
          link: "https://www.youtube.com/user/stdmaxvideo",
        },
        {
          icon: "instagram-color",
          link: "https://www.instagram.com/maxvideo_wed/",
        },
      ]
    }
  }
}
</script>
