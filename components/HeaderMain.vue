<template>
    <header>
      <div class="header-container">
        <NuxtLink to="/">
          <Logo class="logo" />
        </NuxtLink>
        <nav class="nav-main">
          <ul class="nav-list">
            <li v-for="(link, index) in navLinks" class="nav-list-item" :key="link.title" >
              <div v-on:mouseover="link.subNavShow = true" class="nav-link-container">
                <NuxtLink  :to="link.link" class="nav-link link-hover">{{link.title}}</NuxtLink>
              </div>
              <div v-show="link.subNavShow" v-on:mouseleave="link.subNavShow = false" v-if="link.subNav.length !==0" class="sub-nav-container">
                <ul class="nav-sub-list">
                  <li v-for="subLink in link.subNav" class="nav-sub-list-item">
                    <NuxtLink :to="subLink.link" class="nav-link link-hover">{{subLink.title}}</NuxtLink>
                  </li>
              </ul>
              </div>
            </li>
          </ul>
        </nav>
        <ButtonMain class="button" label="Связаться" color="red" transparent @click="$emit('clickFeedback')"/>
      </div>
  </header>
</template>

<style lang="scss">
  header
  {
    .header-container
    {
      max-width: 1484px;
      padding: 0px 22px;
      display: flex;
      width: 100%;
      justify-content: space-between;
      align-items: center;
      height: 100%;
      margin: auto;
    }

    .button{
      margin-left: 50px;
      width: 114px;
      height: 28px;
      font-size: 1rem;
    }

    .logo
    {
      //<--8 3 178 34-->
      height: 48px;
      width: 178px;
    }

    background: $secondary-color;
    @include shadow-down;
    border-radius: 0px 0px 15px 15px;
    height: $header-height;

    position: relative;
    z-index: 10;

    .nav-main{
      display: flex;
      font-weight: 400;
    }

    .nav-list{
      display: flex;
      list-style-type: none;
      li:not(:first-child)
      {
        margin-left: 32px;
        font-size: 1rem;
      }
    }

    .nav-link{
      color: white;
      text-decoration: none;
    }

    .nav-list-item {
      z-index: 11;
      position: relative;
    }

    .nav-sub-list{
      background-color: $secondary-color;
      border-radius: 15px;

      padding: 7px 15px;

      display: flex;
      flex-direction: column;
      align-items: center;
        margin-left: 0px;

      li:not(:first-child)
      {
        margin-left: 0px;
        margin-top: 5px;
        font-size: 1rem;
      }
    }

    .sub-nav-container {
      position: absolute;
      height: 190px;
      top: -2px;
      left: -16px;
      border: 41px;
      display: flex;
      align-items: flex-end;
      z-index: -1;
      padding: 10px;
    }

    .link-hover {
      color: $text-white-color;
      transition: .2s;
      &:hover{
        color: $text-white-dark-color;
      }
      &:active{
        color: $text-white-darker-color;
      }
    }
  }


</style>

<script lang="ts">
  export default{
    data (){
      return {
        showSubNav: false,
        navLinks: [
          {title: "Портфолио", link: "/portfolio", subNav: [
              {title:"Свадьбы", link: "/portfolio/wedding"},
              {title:"Дети", link: "/portfolio/ads"},
              {title:"Промо", link: "/portfolio/children"},
              {title:"Клипы", link: "/portfolio/clip"},
            ], subNavShow: false
          },
          {title:"Услуги", link: "/service", subNav: [], subNavShow: false},
          {title: "О нас", link: "/about-us", subNav: [], subNavShow: false},
          {title: "Контакты", link: "/contacts", subNav: [], subNavShow: false}
        ]
      }


    }
  }
</script>

