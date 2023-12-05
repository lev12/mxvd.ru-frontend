<template>
<div class="contact-e-mail">
  <Icon name="e-mail-2" class="contact-e-mail-icon" />
  <a :href=emailLink class="contact-e-mail-link link-hover">{{email}}</a>
</div>
</template>

<style lang="scss">
.contact-e-mail {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  height: 32px;

  .contact-e-mail-icon{
    width: 32px;
    height: 32px;

    margin-right: 16px;
  }

  .contact-e-mail-link {
    @include text-large-font;
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
    email: {
      type: String,
      default: "info@mxvd.ru"
    }
  },
  computed: {
    emailLink () {
      return "mailto:" + this.email;
    }
  }
}
</script>
