<template>
  <div class="telephone-container">
    <span class="title">Телефоны</span>
    <div class="telephone-link" v-for="(item, index) in telephones">
      <a :href="item.link" class="link link-hover">{{item.label}}</a>
    </div>
  </div>
</template>

<style lang="scss">

</style>

<script setup>
  const telephones = [{label: '+7(910)9587229',link: 'tel:+79109587229'},{label: '+7(910)9505427',link: 'tel:+79109505427'}];

</script>
