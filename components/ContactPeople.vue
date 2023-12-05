<template>
  <div class="contact-people">
    <img :src=avatar.link :alt=avatar.alt class="contact-people-avatar">
    <div class="contact-people-info">
      <h2 class="contact-people-name">{{name}}</h2>
      <div class="contact-people-media" v-for="item of media">
        <Icon class="contact-people-media-icon" :name=item.icon />
        <a :href=item.link class="contact-people-media-link link-hover">{{item.anchor}}</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.contact-people {
  height: 300px;
  display: flex;
  flex-direction: row;
  justify-content: start;
  max-width: 900px;

  .contact-people-info{
    width: 300px;
    display: flex;
    flex-direction: column;
    justify-content: center;

    margin-left: 48px;
  }

  .contact-people-avatar{
    height: 300px;
    filter: drop-shadow(4px 4px 4px rgba(0, 0, 0, 0.15));
  }

  .contact-people-name {
    @include h2-font;
    margin-bottom: 12px;
  }

  .contact-people-media {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-bottom: 12px;

    .contact-people-media-icon {
      width: 21px;
      height: 21px;

      margin-right: 12px;

      opacity: 0.3;
    }

    .contact-people-media-link {
      @include text-font;
    }
  }

  .link-hover {
    color: $text-black-color;
    transition: .2s;
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
    avatar: {
      type: Object,
    },
    name: {
      type: String,
      default: "ФИО",
    },
    media: {
      type: Array
    }
  }
}
</script>
