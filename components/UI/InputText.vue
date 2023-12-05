<template>
<input type="text" class="input-text"
  :placeholder="placeholder">
</template>

<style lang="scss">
.input-text{
  @include text-font;
  border-radius: 10px;
  padding: 6px 8px;
  border: 1px solid $text-black-lighter-color;
}
</style>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      default: "Введите текст"
    }
  }
}
</script>
