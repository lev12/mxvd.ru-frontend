<template>
<div class="video-description-container">
  <p class="video-description-text" v-html="transformed"></p>
</div>
</template>

<style lang="scss">
.video-description-container {
  .video-description-text {
    @include text-medium-font;
    color: $text-black-color;
    font-weight: 400;
  }

  .link-hover{
    color: $secondary-color;
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
    text: {
      type: String
    }
  },
  methods: {
    convertHashTags: function(str) {
      const spanned = `${str}`
      return spanned.replace(/#(\S+)/g,'<a class="link-hover" href="/tag/$1">#$1</a>')
    }
  },
  computed: {
    transformed () {
      const template = this.convertHashTags(this.text);
      console.log(template);
      return template
    }
  }
}
</script>
