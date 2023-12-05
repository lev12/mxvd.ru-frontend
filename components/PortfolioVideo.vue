<template>
<div class="portfolio-video-container">
  <VideoCardGrid v-for="chunk in videoSetChunk" :videoSet="chunk" :rowCount="2" :columnCount="2"/>

</div>
</template>

<style lang="scss">
.push-enter-active,
.push-leave-active {
  transition-property: opacity;
  transition-timing-function: ease-in-out;
  transition-duration: 1000ms;
}

.push-enter,
.push-leave-to {
  opacity: 0;
}

</style>

<script>
export default {

  data () {
    return {
      videoSetChunk: [
        [
            {
            title: "Танцевальный проект \"ВЕРФЬ\"",
            time: "3:15",
            img: "https://mxvd.ru/files/portfolio/img/Shipyard_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Shipyard_preview.mp4",
            url: "test1"
          }, {
            title: "СЕРГЕЙ И ЕКАТЕРИНА",
            time: "4:22",
            img: "https://mxvd.ru/files/portfolio/img/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.mp4",
            url: "test2"
          }, {
            title: "Владимир и Надежда",
            time: "02:58",
            img: "https://mxvd.ru/files/portfolio/img/Wedding_July_20_2019_Vladimir_and_Nadezhda_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Wedding_July_20_2019_Vladimir_and_Nadezhda_preview.mp4",
            url: "test3"
          }, {
            title: "Сергей Чумаков - Русь",
            time: "03:15",
            img: "https://mxvd.ru/files/portfolio/img/Sergey_Chumakov-Rus_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Sergey_Chumakov-Rus_preview.mp4",
            url: "test4"
          }
        ],
        [
        {
            title: "Танцевальный проект \"ВЕРФЬ\"",
            time: "3:15",
            img: "https://mxvd.ru/files/portfolio/img/Shipyard_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Shipyard_preview.mp4",
            url: "test1"
          }, {
            title: "СЕРГЕЙ И ЕКАТЕРИНА",
            time: "4:22",
            img: "https://mxvd.ru/files/portfolio/img/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.mp4",
            url: "test2"
          }, {
            title: "Владимир и Надежда",
            time: "02:58",
            img: "https://mxvd.ru/files/portfolio/img/Wedding_July_20_2019_Vladimir_and_Nadezhda_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Wedding_July_20_2019_Vladimir_and_Nadezhda_preview.mp4",
            url: "test3"
          }, {
            title: "Сергей Чумаков - Русь",
            time: "03:15",
            img: "https://mxvd.ru/files/portfolio/img/Sergey_Chumakov-Rus_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Sergey_Chumakov-Rus_preview.mp4",
            url: "test4"
          }
        ],
        [
        {
            title: "Танцевальный проект \"ВЕРФЬ\"",
            time: "3:15",
            img: "https://mxvd.ru/files/portfolio/img/Shipyard_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Shipyard_preview.mp4",
            url: "test1"
          }, {
            title: "СЕРГЕЙ И ЕКАТЕРИНА",
            time: "4:22",
            img: "https://mxvd.ru/files/portfolio/img/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.mp4",
            url: "test2"
          }, {
            title: "Владимир и Надежда",
            time: "02:58",
            img: "https://mxvd.ru/files/portfolio/img/Wedding_July_20_2019_Vladimir_and_Nadezhda_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Wedding_July_20_2019_Vladimir_and_Nadezhda_preview.mp4",
            url: "test3"
          }, {
            title: "Сергей Чумаков - Русь",
            time: "03:15",
            img: "https://mxvd.ru/files/portfolio/img/Sergey_Chumakov-Rus_preview.jpg",
            video: "https://mxvd.ru/files/portfolio/video/Sergey_Chumakov-Rus_preview.mp4",
            url: "test4"
          }
        ],
      ]
    }
  },
  props:{
    category: {
      type: String,
      required: true,
      default: "all"
    }
  }
}
</script>
