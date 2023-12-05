<template>
      <div class="service">
        <h2 class="service-title-main">Чем мы занимаемся?</h2>
        <div class="service-list">
        <ServiceCard class="service-list_item" v-for="service in services"
                      :title=service.title :description=service.description
                      :img=service.img :link=service.link />
        </div>
    </div>
</template>

<style lang="scss">
  .service {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 50px;
  }

  .service-title-main {
    @include h1-font;
  }

  .service-list {
    display: flex;
    margin: auto;
    justify-content: space-between;
    width: 95%;
    margin-top: 10px;
  }
</style>

<script lang="ts">
export default{
  data () {
    return {
      services: [
        {title: "Свадьбы",
         description: "Свадьба — это событие, которое запоминается на всю жизнь. Детали имеют свойство со временем забываться. Поэтому свадебное видео должно быть идеальным. ",
         img: {src: "/img/1.jpg", alt: "Свадьбы"},
         link: "/service#wedding"},
        {title: "Школы",
         description: "Аттестаты торжественно на сцене вручены. Шарики запущены в небо. Можно начинать праздновать.  Звучит песня «Последний звонок» в исполнении учащихся.",
         img: {src: "/img/2.jpg", alt: "Свадьбы"},
         link: "/service#school"},
        {title: "Праздники",
         description: "Праздничное видео - это видео со  дня рождения, юбилея других торжественных мероприятий. Это поздравления родных и близких, друзей, коллег. ",
         img: {src: "/img/3.jpg", alt: "Свадьбы"},
         link: "/service#event"},
        {title: "Продакшн",
         description: "Мы работаем в сфере коммерческого производства, телевизионной рекламы, наружной рекламы и интернет-рекламы. Наша работа заключается в предоставлении качественных услуг.",
         img: {src: "/img/4.jpg", alt: "Свадьбы"},
         link: "/service#prodution"}
      ]
    }
  }
}
</script>
