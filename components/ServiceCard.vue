<template>
  <div class="service-card">
    <img :src=img.src :alt=img.alt class="service-img">
    <span class="service-title">{{title}}</span>
    <p class="service-description">{{description}}</p>
    <ButtonMain class="service-button" label="Подробнее" color="white" @click="pushToLink()"/>
  </div>
</template>

<style lang="scss">
.service-card{
  width: 324px;
  height: 398px;

  display: flex;
  flex-direction: column;
  padding: 20px;
  border-radius: 16px;

  .service-img{
    width: 268px;
    border-radius: 10px;
  }

  .service-title{
    @include h2-font;
    margin-top: 16px;
  }

  .service-description{
    @include text-font;
    margin-top: 5px;
  }

  .service-button{
    margin-top: auto;
    height: 32px;
  }
}
</style>

<script>
export default {
  props: {
    title: {
      type: String,
      required: false,
      default: "Название"
    },
    description: {
      type: String,
      required: false,
      default: "Описание услуги"
    },
    img: {
      type: Object,
      required: false,
      default: () => {return {src: "https://mxvd.ru/files/28154508_412777659157268_7584458644649934848_n.jpg", alt: "Куликов Иван и Куликов Андрей Maxvideo"}}
    },
    link: {
      type: String,
      required: false,
      default: ""
    }
  },
  methods: {
    pushToLink () {
      if (this.link !== "") this.$router.push(this.link);
    }
  }
}
</script>
