<template>
  <div class="e-mail-container">
    <span class="title">E-mail</span>
    <a :href=email class="link link-hover">{{label}}</a>
  </div>
</template>

<style lang="scss">
  .e-mail-container{
    display: flex;
    flex-direction: column;
    color: $text-black-color;
  }
</style>

<script lang="ts" setup>
  const props = defineProps({
    label: {
      type: String,
      default: 'info@mxvd.ru'
    },
    email: {
      type: String,
      default: 'mailto:info@mxvd.ru'
    }
  })
</script>
