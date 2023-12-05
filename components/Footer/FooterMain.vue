<template>
  <footer>
    <div class="footer-container">
      <FooterSocialMedia class="footer-item"/>
      <FooterTelephone class="footer-item"/>
      <FooterEmail class="footer-item"/>
    </div>
  </footer>
</template>

<style lang="scss">
footer{
  @include shadow-up;
  background: $secondary-color;
  border-radius: 15px 15px 0px 0px;
  height: $footer-height;

  .footer-container{
    display: flex;
    justify-content: center;

  }

  .footer-item{
    margin-top: 10px;
    color: $text-black-color;
  }
  .footer-item:not(:first-child){
    margin-left: 35px;
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

<script lang="ts" setup>

</script>
