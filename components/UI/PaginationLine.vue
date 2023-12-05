<template>
<div class="pagination-line-container">
  <div class="pagination-line_item-container"
        v-for="index in length" :key="index" @click="$emit('click', index); currentSelect=index">
    <div v-bind:class="{ 'active': currentSelect==index }" class="pagination-line_item"></div>
  </div>
</div>
</template>

<style lang="scss">
.pagination-line-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  max-width: v-bind(widthContainer());

  .pagination-line_item-container:not(:first-child)
  {
    margin-left: 32px;
  }

  .pagination-line_item-container {
    height: 32px;
    width: 100%;
    background-color: $primary-color;
    display: flex;
    align-items: center;
    cursor: pointer;

    &:hover{
      :only-child:not(.active){background-color: $primary-darker-color;}
    }
    .active {
      background-color: $secondary-color;
    }
  }

  .pagination-line_item {
    height: 3px;
    width: 100%;

    transition: background-color 0.2s linear;
    background-color: $gray-lighter-color;


  }


}

</style>

<script>
export default {
  data: () => {
    return {
      currentSelect: 1,
    }
  },
  props: {
    length: { type: Number, required: true }
  },
  methods: {
    widthContainer() {
      return this.length*128 + "px";
    }
  }
}
</script>
