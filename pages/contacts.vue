<template>
  <div class="content">
    <h1 class="max-width-block margin-top-block title-main">Контакты</h1>
    <ContactPeople v-for="people of peoples" :avatar="people.img" :name="people.name" :media="people.media"
                  class="margin-top-block max-width-block" />
    <ContactSocialMedia  class="margin-top-block max-width-block"/>
    <ContactEmail  class="margin-top-block max-width-block"/>
    <FeedbackCard id="feedback" class="margin-top-block margin-bottom-block max-width-block"/>
  </div>
</template>

<style lang="scss">

</style>

<script>
export default {
  data() {
    return {
      peoples: [
        {
          img: {
            alt: "Иван Куликов",
            link: "https://mxvd.ru/files/ivan_kulikov_portret.png"
          },
          name: "Иван Куликов",
          media: [
            {
              icon: "phone",
              anchor: "+7(910)958-72-29",
              link: "tel:+79109587229"
            },
            {
              icon: "vk",
              anchor: "https://vk.com/ivan_kulikov",
              link: "https://vk.com/ivan_kulikov"
            }
          ]
        },
        {
          img: {
            alt: "Андрей Куликов",
            link: "https://mxvd.ru/files/andrew_kulikov_portret.png"
          },
          name: "Андрей Куликов",
          media: [
            {
              icon: "phone",
              anchor: "+7(910)950-54-27",
              link: "tel:+79109505427"
            },
            {
              icon: "vk",
              anchor: "https://vk.com/kulikovandrei",
              link: "https://vk.com/kulikovandrei"
            }
          ]
        }
      ]
    }
  }
}
</script>
