<template>
  <div class="review-card-last-container">
    <h2 class="review-card-last-title">{{title}}</h2>
    <PaginationLine class="review-card-last-pagination" :length="reviews.length" @click="changeActiveReview" />
    <div class="review-card-last-list-container-hidden" ref="containerHide">
      <div class="review-card-last-list-container" ref="container">
        <ReviewCard class="review-card-last-card" v-for="review in reviews"
          :author="review.author" :avatar="review.avatar"
          :postLink="review.postLink" :text="review.text"
          :video="review.video" :reviewLink="review.reviewLink" />
      </div>
    </div>

    <ButtonMain class="review-card-last-button" :label="buttonLabel" color="white" @click="toReview()"/>
  </div>
</template>

<style lang="scss">
.review-card-last-container{
  display: flex;
  flex-direction: column;
  align-items: center;


  .review-card-last-title {
    @include h1-font;
    margin-bottom: 16px;
  }

  .review-card-last-pagination {
    margin-bottom: 20px;
  }

  .review-card-last-list-container-hidden {
    width: 100%;
    height: 450px;
    overflow: hidden;
    position: relative;
    transition: 2s;


  }

  .review-card-last-list-container-hidden::after {
    content: '';
    width: 50px;
    height: 100%;
    position: absolute;
    right: 0;
    top: 0;
    z-index: 10;
    background: linear-gradient(90deg, rgba(2,0,36,0) 0%, rgba(255,255,255,1) 100%);
  }

  .review-card-last-list-container-hidden::before {
    content: '';
    width: 50px;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
    z-index: 10;
    background: linear-gradient(-90deg, rgba(2,0,36,0) 0%, rgba(255,255,255,1) 100%);
  }

  .review-card-last-list-container {
    margin-bottom: 16px;
    display: inline-flex;
    position: absolute;
    transition: left 2s ease-in-out;

    left: v-bind('reviewShift');

    .review-card-last-card:not(:first-child) {
      margin-left: 80px;
    }
  }

  .review-card-last-button {
    width: 285px;
    height: 34px;
  }
}

</style>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Отзывы"
    },
    buttonLabel: {
      type: String,
      default: "Все отзывы"
    }
  },
  data (){
    return {
      activeReview: 1,
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
            previewImg: "https://mxvd.ru//files/portfolio/img/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_July_12_2019_Sergey_and_Ekaterina_preview.mp4",
            link: "1"
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
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_September_07_2019_Eldar_and_Julia_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_September_07_2019_Eldar_and_Julia_preview.mp4",
            link: "2"
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
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_July_20_2018_Victor_and_Nadezhda_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_July_20_2018_Victor_and_Nadezhda_preview.mp4",
            link: "3"
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
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_June_9_2017_Dmitry_and_Ksenia_preview.jpg",
            previewVideo: "https://mxvd.ru/files/portfolio/video/Wedding_June_9_2017_Dmitry_and_Ksenia_preview.mp4",
            link: "4"
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
            previewImg: "https://mxvd.ru/files/portfolio/img/Wedding_April_21_2017_Dmitry_and_Daria_preview.jpg",
            previewVideo: "https://mxvd.ru//files/portfolio/video/Wedding_April_21_2017_Dmitry_and_Daria_preview.mp4",
            link: "5s"
          }
        },
      ]
    }
  },
  computed: {
    reviewShift () {
      if (this.$refs.container == null) return 0;
      return -((this.$refs.container.clientWidth - this.$refs.containerHide.clientWidth + 100)/ (this.reviews.length-1) * (this.activeReview-1) - 50) + "px";
    }
  },
  methods:
  {
    changeActiveReview (index){
      this.activeReview = index
    },
    updateShift()
    {
      this.activeReview++;
      this.activeReview--;
    },
    toReview() {
      this.$router.push('/review');
    }
  },
  mounted: function () {
    this.$nextTick(function () {
      this.updateShift();
    })
    window.addEventListener('resize', this.updateShift)
  },
}
</script>
