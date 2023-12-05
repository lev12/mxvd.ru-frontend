<template>
  <button
    :class="['btn', `btn_${color+transparentClassConvert(transparent)}`, {'btn_outlined': outlined}, {'btn_blur': blur}]"
    :disabled="disabled"
    @click="clickOnButton">
      <span class="btn-label">{{label}}</span>
    </button>
</template>

<style lang="scss" >
.btn {
  @include button-font;

  height: 40px;
  color: #fff;
  border-radius: 10px;
  border: none;
  cursor: pointer;
  transition: .2s;

  .btn-label{
    margin: 2px 4px;
  }

  &_red {
    background: $accent-color;
    border: 1px solid $accent-color-dark;
    color: $text-white-color;
    &:enabled:hover {
      background: $accent-color-light;
    }
    &:enabled:active {
      background: $accent-color-dark;
    }
  }

  &_red_t {
    background: transparentize($accent-color, 0.4);
    color: $text-white-color;
    &:enabled:hover {
      background: transparentize($accent-color-light, 0.4);
    }
    &:enabled:active {
      background: transparentize($accent-color-dark, 0.4);
    }
  }

  &_blue {
    background: $secondary-color;
    border: 1px solid $secondary-dark-color;
    color: $text-white-color;
    &:enabled:hover {
      background: $secondary-light-color;
    }
    &:enabled:active {
      background: $secondary-dark-color;
    }
  }

  &_blue_t {
    background: transparentize($secondary-color, 0.4);
    border: 1px solid transparentize($secondary-dark-color, 0.4);
    color: $text-white-color;
    &:enabled:hover {
      background: transparentize($secondary-light-color, 0.4);
    }
    &:enabled:active {
      background: transparentize($secondary-dark-color, 0.4);
    }
  }

  &_white {
    background: $primary-color;
    border: 1px solid #525252;
    color: $text-black-lighter-color;
    &:enabled:hover {
      background: $primary-dark-color;
    }
    &:enabled:active {
      background: $primary-darker-color;
    }
  }

  &_white_t {
    background: transparentize($primary-color, 0.4);
    border: 1px solid transparentize($primary-dark-color, 0.4);
    color: $text-black-lighter-color;
    &:enabled:hover {
      background: transparentize($primary-dark-color, 0.4);
    }
    &:enabled:active {
      background: transparentize($primary-darker-color, 0.4);
    }
  }

  &:disabled {
    opacity: .6;
    cursor: default;
  }
  &_outlined {
    background: transparent;
    color: #000;
    &:hover {
      color: #fff;
    }
  }
}
</style>

<script lang="ts" setup>
  const props = defineProps({
  label: {
    type: String,
    default: 'Button'
  },
  color: {
    type: String,
    default: "red"
  },
  disabled: {
    type: Boolean,
    required: false
  },
  outlined: {
    type: Boolean,
    required: false
  },
  transparent: {
    type: Boolean,
    required: false
  },
  blur: {
    type: Boolean,
    required: false
  }
})

function transparentClassConvert(t: Boolean) {if (t) return "_t"; else return"";};


const emit = defineEmits(['click'])
const clickOnButton = (e:Event) => {
  e.preventDefault();
  emit('click')
}

</script>
