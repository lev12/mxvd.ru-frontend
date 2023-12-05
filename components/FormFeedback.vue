<template>
<form class="form-feedback-container">
  <InputText class="form-feedback-name" placeholder="Введите текст"/>
  <InputContact class="form-feedback-contact" />
  <TextArea class="form-feedback-text" placeholder="Введите вопрос" />
  <div class="form-feedback-personal-data-policy-container">
    <CheckBox class="form-feedback-personal-data-policy-checkbox"/>
    <p class="form-feedback-personal-data-policy-info">
      Нажимая на кнопку, вы даете согласие на обработку своих персональных данных.
    </p>
  </div>
  <ButtonMain class="form-feedback-submit" label="Отправить" />
</form>
</template>

<style lang="scss">
.form-feedback-container {
  //height: 540px;
  width: 640px;

  display: flex;
  flex-direction: column;
  //padding: 25px;

  .form-feedback-contact {
    margin-top: 12px;
  }

  .form-feedback-text {
    min-height: 144px;
    max-height: 256px;
    margin-top: 12px;
    resize: vertical;
  }


  .form-feedback-personal-data-policy-container {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-top: 12px;

    .form-feedback-personal-data-policy-info {
      @include text-small-font;
      line-height: 100%;

      margin-left: 12px;
    }
  }

  .form-feedback-submit{
    height: 34px;
    width: 136px;

    align-self: end;
    margin-top: 18px;
  }
}
</style>

<script>
export default {
  data: () => {
    return {

    }
  }
}
</script>
