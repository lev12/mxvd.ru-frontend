<template>
  <div class="about-us-card">
    <img :src=img.src :alt=img.alt class="about-us-img">
    <p class="about-us-text">{{text}}</p>
  </div>
</template>

<style lang="scss">
  .about-us-card{
    display: flex;
    flex-direction: row;
    width: 1290px;
    align-items: center;
    margin-left: auto;
    margin-right: auto;
  }

  .about-us-img{
    @include shadow-down-right;
    height: 350px;
    border-radius: 1000px;
  }

  .about-us-text{
    @include text-font;
    margin-left: 90px;
  }
</style>

<script lang="ts">
export default {
  props: {
    text: {
      type: String,
      required: false,
      default: "Студия MAX-video- это слаженная команда профессионалов, помогающая Вам сохранить на долгую память неповторимые моменты Вашей жизни. Мы работаем с 2006 года и зарекомендовали себя как ответственные и исполнительные мастера своего дела. Мы работаем во многих направлениях видеосъемки: свадебная, концертная, рекламная. Мы не стоим на месте, а постоянно совершенствуем качество нашей работы и хотим это делать вместе с Вами. Очень надеемся что наша работа принесет Вам радость."
    },
    img: {
      required: false,
      default: () => {return {src: "https://mxvd.ru/files/28154508_412777659157268_7584458644649934848_n.jpg", alt: "Куликов Иван и Куликов Андрей Maxvideo"}}
    },
  }
}
</script>
