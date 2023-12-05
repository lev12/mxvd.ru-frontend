<template>
  <div v-html="src"></div>
</template>
<script>

export default {
   computed: {
       src() { return require(`~/assets/logo/maxvideo-logo.svg?raw`); }
   }
}
</script>
