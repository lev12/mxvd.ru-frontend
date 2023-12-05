<template>
  <div class="showreal-card">
    <div class="showreal-container">
      <h1 v-if="h1Title" class="showreal-title">{{title}}</h1>
      <h2 v-else class="showreal-title">{{title}}</h2>
      <span class="showreal-description" v-if="description.length !== 0">{{description}}</span>
      <div class="showreal-actions">
        <ButtonMain v-for="button in buttons" class="showreal-button" :label=button.text @click=button.callback
         :color=button.color transparent/>
      </div>
    </div>
    <div v-if=showArrowDown class="showreal-arrow" >
      <Icon name="arrow-down" @click="$emit('down')"/>
    </div>
    <div class="showreal-video-container">
      <video class="showreal-video" :src=showrealSrc autoplay loop></video>
    </div>
  </div>
</template>

<style lang="scss">
  .showreal-container{
    $showreal-container-height: 200px;
    $showreal-container-width: 410px;

    position: absolute;
    top: calc(50% - ($showreal-container-height / 2));
    left: calc(50% - ($showreal-container-width / 2));
    height: $showreal-container-height;
    width: $showreal-container-width;
    z-index: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #fff;
    justify-content: space-between;
  }

  .showreal-card{
    height: 540px;
    position: relative;
    align-content: center;

    @include shadow-down;
    border-radius: 15px;
    overflow: hidden;
  }

  .showreal-title{
    font-size: 75px;
    font-weight: 700;
  }

  .showreal-description{
    font-size: 32px;
    font-weight: 300;
    margin-top: -16px;
  }

  .showreal-video-container{
    position: absolute;
    height: 100%;
  }

  .showreal-arrow{
    position: absolute;
    bottom: 8px;
    left: 50%;
    filter: invert(100%);
    z-index: 1;

    height: 24px;
    width: 24px;

    animation-duration: 2s;
    animation-iteration-count: infinite;
      animation-fill-mode: both;
      animation-timing-function: ease;

    &:hover {
      animation-name: bounce;
    }

    @keyframes bounce {
      0%   { transform: translateY(0); }
      50%  { transform: translateY(-5px); }
      100% { transform: translateY(0); }
    }
  }



  .showreal-video{
    display: block;
    position: relative;
    width: 100%;
    top: 50%;
    left: 50%;
    margin-right: -50%;
    transform: translate(-50%, -50%);
    filter: brightness(0.4);
  }

  .showreal-actions{
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin-top: 16px;
  }

  .showreal-button{
    height: 32px;
    width: 192px;
  }
</style>

<script lang="ts">
export default {
  props: {
    title: {
      type: String,
      required: false,
      default: "Maxvideo"
    },
    description: {
      type: String,
      required: false,
      default: "Студия видеографии"
    },
    buttons: {
      required: false,
      default: () => [{text: "Смотреть шоурил", color: "red", callback: ()=>{console.log("1"); return;}},
                      {text: "Заказать видео", color: "blue", callback: ()=>{console.log("2"); return;}}]
    },
    showrealSrc: {
      type: String,
      default: "https://mxvd.ru/files/Showreel%20maxvideo++.mp4"
    },
    showArrowDown: {
      type: Boolean,
      default: true
    },
    h1Title: {
      type: Boolean,
      default: true
    }
  },
  methods: {
    transparentConvert(t: boolean): boolean {
      return t;
    }
  }
}
</script>
