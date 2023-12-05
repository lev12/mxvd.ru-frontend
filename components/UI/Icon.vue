<template>
  <div class="icon" @click="$emit('click')">
    <svg
      fill="currentColor"
      :viewBox="'0 0 ' + width + ' ' + height"
      xmlns="http://www.w3.org/2000/svg"
      data-testid="base-icon"
      v-html="src"
    ></svg>
  </div>
</template>
<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    height: {
      type: Number,
      required: false,
      default: 32
    },
    width: {
      type: Number,
      required: false,
      default: 32
    },
  },

  computed: {
    src() {
      const body = require(`assets/icon/${this.name}.svg?raw`);
      return body;
    }
  }
}
</script>
