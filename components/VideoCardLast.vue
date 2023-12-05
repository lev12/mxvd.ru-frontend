<template>
  <div class="video-card-last-container">
    <h2 class="video-card-last-title">{{title}}</h2>
    <VideoCardGrid class="video-card-last-grid" :rowCount="2" :columnCount="2" :videoSet="videos" @click="view" />
    <ButtonMain class="video-card-last-button" label="Все работы" color="white" />
  </div>
</template>

<style lang="scss">
.video-card-last-container {
  display: flex;
  flex-direction: column;
  align-items: center;

  .video-card-last-title {
    @include h1-font;
    margin-bottom: 28px;
  }

  .video-card-last-grid {
    //width: 1312px;
    width: 100%;
    margin: auto;
  }

  .video-card-last-button {
    width: 285px;
    height: 34px;
  }
}
</style>

<script lang="ts">
export default {
  data () {
    return {
      title: "Последние работы",
      videos: [{
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
      }]
    }
  },
  methods: {
    view (videodata: Object) {
      console.log(videodata);
    },
  }
}
</script>
