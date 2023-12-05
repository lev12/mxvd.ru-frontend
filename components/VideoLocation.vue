<template>
<div class="video-location-container">
  <Icon name="location" class="video-location-icon" />
  <NuxtLink :to="'/location/' + location.alias" class="video-location-text link-hover"><span>{{location.name}}</span></NuxtLink>
</div>
</template>

<style lang="scss">
.video-location-container {
  display: flex;
  flex-direction: row;
  align-items: center;

  .video-location-icon {
    width: 32px;
    height: 32px;
  }

  .video-location-text {
    @include text-medium-font;
    color: $text-black-color;
  }

  .link-hover{

    transition: all .2s linear;
    &:hover{
      color: $text-black-lighter-color;
    }
    &:active{
      color: $text-black-light-color;
    }
  }
}
</style>

<script>
export default {
props: {
  location: {
    type: Object,
    required: true
  }
}
}
</script>
