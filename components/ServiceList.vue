<template>
<div class="service-list-container">
  <Service class="service-list_item"
           v-for="service of services" :id="service.id"
           :title="service.title" :showrealSrc="service.showrealSrc"
           :blocks="service.blocks" :videos="service.videos" :videoMoreLink="service.videoMoreLink" />
</div>
</template>

<style lang="scss">
.service-list-container {
  .service-list_item:not(:first-child) {
    margin-top: 96px;
  }
}
</style>

<script>
export default {
  data () {
    return {
      services: [
        {
          id: "wedding",
          title: "Свадьбы",
          showrealSrc: "https://mxvd.ru/files/Showreel%20maxvideo++.mp4",
          actionButtons: [
            {text: "Смотреть шоурил", color: "red", callback: ()=>{console.log("1"); return;}},
            {text: "Заказать видео", color: "blue", callback: ()=>{console.log("2"); return;}}
          ],
          blocks: [
            {
              title: "Свадьба",
              description: "Свадьба — это событие, которое запоминается на всю жизнь. Детали имеют свойство со временем забываться. Поэтому свадебное видео должно быть идеальным. Свадебная съемка — это всегда эмоции, слова и действия, которые должны быть запечатлены на камеру. Сборы, регистрация, прогулка и банкет — все объединено в один фильм. В конце дня вы обязательно захотите взглянуть на себя, чтобы вспомнить, как прошёл это  свадебный день. ",
              image: {
                src: "/img/service/1.png",
                alt: ""
              }
            },
            {
              title: "Love story",
              description: "Мы сохраним воспоминания вашего знакомства и любви. В этой истории вы главные герои. События, которые с ними происходили, будут основой. Сценаристы: вы и любовь. Режиссер: ваша память. Композитор: воспоминания. Это открывает  простор для творчества.  Потому, что история любви у каждой пары своя, а значит, и концепция роликов уникальна. Из-за этого ролики ниже не похожи друг на друга. ",
              image: {
                src: "/img/service/2.png",
                alt: ""
              }
            }
          ],
          videos: [
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
            }
          ],
          videoMoreLink: ""
        },
        {
          id: "school",
          title: "Школы",
          showrealSrc: "https://mxvd.ru/files/Showreel%20maxvideo++.mp4",
          actionButtons: [
            {text: "Смотреть шоурил", color: "red", callback: ()=>{console.log("1"); return;}},
            {text: "Заказать видео", color: "blue", callback: ()=>{console.log("2"); return;}}
          ],
          blocks: [
            {
              title: "Один день из жизни класса",
              description: "В этом видео вы увидите, как проходят уроки в  школе: как учатся дети, какие задания получают на уроке, как проходят эксперименты на уроке химии, что происходит на перемене, смешные моменты и многое другое.",
              image: {
                src: "/img/service/3.png",
                alt: ""
              }
            },
            {
              title: "Выпускной",
              description: "Аттестаты торжественно на сцене вручены. Шарики запущены в небо. Можно начинать праздновать. Выпускной вечер в 9 или 11 классе. Звучит песня «Последний звонок» в исполнении учащихся. Ведущий: Добрый день, дорогие друзья! Сегодня мы собрались на праздник, который по традиции называется «Выпускной». Он всегда бывает грустным потому, что дети покидают школу и любимых учителей”.",
              image: {
                src: "/img/service/4.png",
                alt: ""
              }
            }
          ],
          videos: [
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
            }
          ],
          videoMoreLink: ""
        },
        {
          id: "event",
          title: "Event",
          showrealSrc: "https://mxvd.ru/files/Showreel%20maxvideo++.mp4",
          actionButtons: [
            {text: "Смотреть шоурил", color: "red", callback: ()=>{console.log("1"); return;}},
            {text: "Заказать видео", color: "blue", callback: ()=>{console.log("2"); return;}}
          ],
          blocks: [
            {
              title: "Праздники",
              description: "Мы снимаем и другие мероприятия. Всегда рады вам помочь. Праздничное видео - это видео со  дня рождения, юбилея других торжественных мероприятий. Это поздравления родных и близких, друзей, коллег. ",
              image: {
                src: "/img/service/5.png",
                alt: ""
              }
            }
          ],
        },
        {
          id: "prodution",
          title: "Prodution",
          showrealSrc: "https://mxvd.ru/files/Showreel%20maxvideo++.mp4",
          actionButtons: [
            {text: "Смотреть шоурил", color: "red", callback: ()=>{console.log("1"); return;}}
          ]
        }
      ]
    }

  }
}
</script>
