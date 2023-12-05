<template>
  <div class="content">
    <h1 class="max-width-block margin-top-block title-main">#{{tag}}</h1>
    <p v-if="descrition.length !== 0" class="max-width-block tag-subtitle">{{descrition}}</p>
    <VideoCardGrid class="max-width-block margin-top-block" v-for="chunk in videoSetChunk" :videoSet="chunk" :rowCount="2" :columnCount="2"/>
  </div>
  </template>

  <style lang="scss">
  .tag-subtitle {
    @include text-medium-font;
    text-align: center;
    max-width: 900px;
    margin-top: 8px;
    display: flex;
    justify-content: center;
  }
  </style>

  <script>
  export default {
    data() {
      return {
        tag: "спорт",
        descrition: "Короче, спорт — способ не только хорошо провести время, но и немного похудеть.",
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
    }
  }
  </script>
