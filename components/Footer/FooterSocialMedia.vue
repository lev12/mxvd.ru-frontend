<template>
  <div class="social-media-container">
    <span class="title">Социальные сети</span>
    <div class="social-media-icon-container">
      <a class="link link-hover" v-for="(item, index) in socialMedia" :href="item.link">
        <Icon :name="item.icon" class="social-media-icon" />
      </a>
    </div>
  </div>
</template>

<style lang="scss">
  .social-media-icon{
    width: 32px;
    height: 32px;
    filter: invert(0%);
    transition: all 0.5s ease;
  }

  .social-media-icon:hover {
    filter: invert(15%);
  }

  .social-media-icon-container
  {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    margin-top: 5px;

  }
  //  <a :href="item.link" class="link link-hover" v-for="(item, index) in socialMedia"><Icon :name="item.icon"  class="icon"/></a>
</style>

<script setup>
  const socialMedia = [{icon: 'vk-circle-black',link: 'http://vk.com/stdmaxvideo'},
                {icon: 'youtube-circle-black',link: 'https://www.youtube.com/user/stdmaxvideo'},
                {icon: 'instagram-circle-black',link: 'https://www.youtube.com/user/stdmaxvideo'}
              ];

</script>
