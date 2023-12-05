<template>
<textarea class="text-area" @input="resize()" ref="textarea" :placeholder="placeholder"></textarea>
</template>

<style lang="scss">
.text-area {
  @include text-font;
  border-radius: 10px;
  padding: 6px 8px;
  border: 1px solid $text-black-lighter-color;

  resize: none;
}

::-webkit-resizer {
  display: none;
}


</style>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      default: "Введите текст"
    }
  },

  methods: {
    resize() {
      let element = this.$refs["textarea"];

      element.style.height = "18px";
      element.style.height = element.scrollHeight+2 + "px";
    },
  },
}
</script>
