<template>
<div class="review-loader-container">
  <Review class="review-loader" v-for="review in reviews"
          :author="review.author" :avatar="review.avatar"
          :postLink="review.postLink" :text="review.text"
          :video="review.video" :reviewLink="review.reviewLink" />
</div>
</template>

<style lang="scss">
.review-loader-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .review-loader {
    display: flex;

    &:not(:first-child)
    {
      margin-top: 24px;
    }
  }

}
</style>

<script>
export default {
  data() {
    return {
    reviews: [
        {
          reviewLink: "",
          author: "Екатерина Швец",
          avatar: {
            link: "/img/Ekaterina-Shvets.jpg",
            alt: "",
          },
          postLink: "https://vk.com/stdmaxvideo?w=wall-28683644_901",
          text: "Я думаю, что уже не раз звучали слова благодарности в адрес студии Мaxvideo. Мы с супругом не будем исключением)\nНам посчастливилось работать с Иваном в день нашей свадьбы.\nЭто ПРОФЕССИОНАЛ своего дела с большой буквы! Восхищение вызывает не только ПОТРЯСАЮЩИЙ результат его работы, но и само отношение к процессу съемки. Тому подтверждением один из случаев на нашей свадьбе. Во время выездной регистрации, когда съемка велась не только с земли, но и воздуха, произошло внезапное падение квадрокоптера в реку. При этом Иван ни на секунду не приостановил съемку, проявив максимальное самообладание и профессионализм. И только после окончания церемонии вернулся к спасению \"утопающего\")).\nПри создании и монтаже видео смог детально подчеркнуть и передать настроение свадьбы, подобрал максимально подходящее аудио-сопровождение и учел все наши пожелания.\nИсходя из вышесказанного, советуем всем тем, кто стоит на пути выбора видеографа и читает этот отзыв, доверить свое событие студии Мaxvideo!\nВ выборе видеографа на свою свадьбу мы ТОЧНО НЕ ОШИБЛИСЬ!\nОгромное Вам СПАСИБО!",
          video: {
            title: "СЕРГЕЙ И ЕКАТЕРИНА",
            time: "03:45",
            previewImg: "https://mxvd.ru//files/portfolio/img/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.mp4",
            link: ""
          }
        },
        {
          reviewLink: "",
          author: "Eldar Gismatulin",
          avatar: {
            link: "/img/Eldar-Gismatulin.jpg",
            alt: "",
          },
          postLink: "https://vk.com/stdmaxvideo?w=wall-28683644_899",
          text: "Хотим выразить огромную благодарность студии Maxvideo! Тем, кто планирует свадьбу или тем, кто хочет просто запечатлеть радостное и значимое событие вашей жизни - однозначно рекомендуем их! Ребята - профессионалы своего дела. Необычно, креативно, трогательно. Видео можно пересматривать 100 раз, и каждый раз смотришь с удовольствием! Мы и все наши друзья просто в восторге! Огромное вам спасибо!",
          video: {
            title: "Эльдар и Юлия",
            time: "03:05",
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_September_07_2019_Eldar_and_Julia_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_September_07_2019_Eldar_and_Julia_preview.mp4",
            link: ""
          }
        },
        {
          reviewLink: "",
          author: "Надежда Элярт",
          avatar: {
            link: "/img/Nadezhda-Elyart.jpg",
            alt: "",
          },
          postLink: "https://vk.com/kulikovandrei?w=wall143377237_995",
          text: "Незабываемый день Спасибо Андрею Куликову за это волшебство.",
          video: {
            title: "ВИКТОР И НАДЕЖДА",
            time: "03:03",
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_July_20_2018_Victor_and_Nadezhda_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_July_20_2018_Victor_and_Nadezhda_preview.mp4",
            link: ""
          }
        },
        {
          reviewLink: "",
          author: "Дмитрий Шокшин",
          avatar: {
            link: "/img/Dmitry-Shokshin.jpg",
            alt: "",
          },
          postLink: "https://vk.com/stdmaxvideo?w=wall-28683644_748",
          text: "Вот уже 2 с половиной месяца прошло после нашей свадьбы и мы получили наше свадебное видео, которое мы очень ждали. Когда мы смотрели этот коротенький фильм, мы словно вернулись в 9 июня 2017 года, вспомнили все его детали, все свадебные хлопоты, заботы, всё что было в этот день. Мне кажется, когда мы будем смотреть этот фильм через многие годы он будет пробуждать в нас ещё более тёплые воспоминания о дне нашей свадьбы и о том какими мы были в самом начале основания нашей семьи.",
          video: {
            title: "ДМИТРИЙ И КСЕНИЯ",
            time: "03:16",
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_June_9_2017_Dmitry_and_Ksenia_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_June_9_2017_Dmitry_and_Ksenia_preview.mp4",
            link: ""
          }
        },
        {
          reviewLink: "",
          author: "Дарья Малютина",
          avatar: {
            link: "/img/Darya-Malyutina.jpg",
            alt: "",
          },
          postLink: "https://vk.com/stdmaxvideo?w=wall-28683644_743",
          text: "Свадебное видео мечты! Спасибо тебе, Иван Куликов, за то, что понял нас и сделал видео, которое хочется пересматривать бесконечно. Enjoy!",
          video: {
            title: "Дмитрий и Дарья",
            time: "03:54",
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_April_21_2017_Dmitry_and_Daria_preview.jpg",
            previewVideo: "https://mxvd.ru//files/portfolio/video/Wedding_April_21_2017_Dmitry_and_Daria_preview.mp4",
            link: ""
          }
        },
      ]
    }
  }
}
</script>
