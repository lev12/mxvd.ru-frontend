<template>
<div class="content anim">
  <h1 class="max-width-block margin-top-block title-main">Портфолио</h1>
  <PortfolioNav class="nav-margin-top-block" :nav="nav"/>
  <PortfolioVideo class="max-width-block margin-top-block video" :category="getCategory()"/>

</div>
</template>

<style lang="scss">
.nav-margin-top-block {
  margin: 24px;
}
.anim {
  overflow: hidden;
}
.video {
  position: relative;
  left:0px;
  transition: v-bind('animationIs')
}

.home-enter { transition: v-bind('animationIs')  ; .video{left: 2000px; opacity: 0; }  }
.home-leave-active { transition: v-bind('animationIs') ; .video{left: -2000px; opacity: 0; }  }

</style>

<script>
export default {
  transition: 'home',
  data () {
    return {
      transition: {
        animation: true,
        left: true
      },
      nav: [
        {
          title: "Все",
          link: "/portfolio"
        },
        {
          title: "Свадьбы",
          link: "/portfolio/wedding"
        },
        {
          title: "Дети",
          link: "/portfolio/children"
        },
        {
          title: "Промо",
          link: "/portfolio/ads"
        },
        {
          title: "Клипы",
          link: "/portfolio/clip"
        },
      ]
    }
  },
  methods: {
    getCategory() {
      let param = this.$router.currentRoute.params.category;
      if (param === null) return "all"
      else return param;
    },
    /*getLeft(from, to) {
      if (typeof from === "undefined") from = this.nav[0].link;
      if (typeof to === "undefined") to = this.nav[0].link;
      let idFrom = -1;
      let idTo = -1;
      for (let i = 0; i < this.nav.length; i++) {
        const element = this.nav[i];
        if (element.link === from) {
          idFrom = i;
          break;
        }
      }

      for (let i = 0; i < this.nav.length; i++) {
        const element = this.nav[i];
        if (element.link === to) {
          idTo = i;
          break;
        }
      }
      return idFrom > idTo;
    }*/
  },
  computed: {
    animationIs () {
      return this.transition.animation ? "all 0.5s ease-in-out" : "none 0s ease-in-out";
    }
  },
  beforeRouteEnter(to, from, next) {
    next(vm => {
      vm.transition.animation = false;
      setTimeout(() => {
        vm.transition.animation = true;
      }, 500);
    })
  },
  beforeRouteUpdate(to, from, next) {
    this.transition.animation = true;
    console.log();
    next()
  },
  beforeRouteLeave(to, from, next) {
    this.transition.animation = false;
    next()
  }
}
</script>
