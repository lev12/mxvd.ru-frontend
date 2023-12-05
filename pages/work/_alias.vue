<template>
<div class="content">
  <VideoPlayerWrapper class="max-width-block video-player" :video="video" />
  <h1 class="title-video video-padding max-width-block">{{title}}</h1>
  <VideoLocation class="max-width-block video-padding" :location="location" />
  <VideoDescription class="max-width-block video-padding" :text="description" />
  <VideoOther class="max-width-block video-padding" :video="videoOther"/>
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
        data: "https://www.youtube.com/embed/WBrcToov-mU"
      },
      title: "Танцевальный проект \"ВЕРФЬ\"",
      description: "#спорт Танцевальный проект \"ВЕРФЬ\" существует уже более 10 лет.За это время проект получил множество наград и стал визитной карточкой города, а его участники - известными во всем мире мастерами.В этом году проект отметит свой юбилей.10 лет!И в честь этого знаменательного события, мы открываем новый сезон.Танцевальный сезон 2019 года будет посвящён празднованию нашего 10-летнего юбилея.Мы объявляем набор в танцевальные группы!Приглашаем всех желающих!Группы для детей и взрослых, для мальчиков и девочек! #аэросъемка",
      location: {
        name: "Кострома",
        alias: "kostroma"
      },
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
