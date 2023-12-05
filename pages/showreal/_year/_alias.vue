<template>
  <div class="content">
    <VideoPlayerWrapper class="max-width-block video-player" :video="video" />
    <h1 class="title-video video-padding max-width-block">{{title}}</h1>
    <VideoOther class="max-width-block video-padding" :video="videoOther" title="Использованные работы" />
  </div>
  </template>

  <style lang="scss">
  .video-player {
    margin-top: 20px;
  }
  .title-video {
    @include h2-font;
    color: $text-black-color;
  }

  .video-padding {
    padding-left: 36px;
    padding-right: 36px;
    padding-top: 20px;

  }
  </style>

  <script>
  export default {
    data() {
      return {
        alias: "shipyard",
        video: {
          typeSrc: "youtube",
          data: "https://www.youtube.com/embed/9PZfhskVzAQ"
        },
        title: "Showreel maxvideo",
        videoOther: [
          {
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
        ]
      }
    }
  }
  </script>
