<template>
  <div class="feedback-card-container">
    <div class="feedback-card-info-container">
      <h1 class="feedback-card-title">{{title}}</h1>
      <p class="feedback-card-subtitle">{{subtitle}}</p>
    </div>
    <FormFeedback />
  </div>
</template>

<style lang="scss">
.feedback-card-container{
  width: 1150px;
  display: flex;
  flex-direction: row;
  align-items: center;

  .feedback-card-info-container{
    display: flex;
    flex-direction: column;

    width: 430px;
    margin-right: 200px;
  }

  .feedback-card-title {
    @include h1-font;
  }

  .feedback-card-subtitle {
    @include text-font;
  }
}
</style>

<script>
export default {
  data: () =>
  {
    return {
      title: "Обратная связь",
      subtitle: "Если у вас появились вопросы, то можете написать здесь и в течении часа вам придёт ответ по указанному средству связи "
    }
  },
}
</script>
