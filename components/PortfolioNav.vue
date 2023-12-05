<template>
<div class="portfolio-nav-container">
  <ul class="portfolio-nav-list">
    <li class="portfolio-nav-list_item" v-for="item in nav"  >
      <NuxtLink :to="item.link" class="link-hover">{{item.title}}</NuxtLink>
    </li>
  </ul>
</div>
</template>

<style lang="scss">
.portfolio-nav-container {
  display: flex;
  flex-direction: row;
  justify-content: center;

  .portfolio-nav-list{
    display: flex;
    flex-direction: row;
    justify-content: space-between;

    width: 100%;
    max-width: 512px;
  }

  .portfolio-nav-list_item {
    :not(:first-child)
    {
      margin-left: 10px;
    }
  }

  .link-hover{
    @include text-font;
    color: $text-gray-color;
    font-weight: 400;

    transition: all .2s linear;
    &:hover{
      color: $text-black-lighter-color;
    }
    &:active{
      color: $text-black-light-color;
    }
  }

  .nuxt-link-exact-active {
    color: $text-black-color;
  }
}
</style>

<script>
export default {
  props: {
    nav : {
      type: Array,
      required: true
    }
  }
}
</script>
