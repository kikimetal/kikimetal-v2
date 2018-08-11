<template>
  <div>
    <nav class="global">
      <router-link :to="{ path: '/', params: {} }" exact><Btn text="home"></Btn></router-link>
      <router-link :to="{ path: '/image', params: {} }" exact><Btn text="image"></Btn></router-link>
      <router-link :to="{ path: '/website', params: {} }" exact><Btn text="website"></Btn></router-link>
    </nav>
    <nuxt/>
  </div>
</template>

<style>
nav.global{
  font-size: 20rem;

  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: auto;
  width: 100%;
  height: 50px;
  padding: 0 .2em;


  display: flex;
  flex-flow: row;
  justify-content: space-around;
  align-items: center;

  background: linear-gradient(90deg, rgb(255, 172, 229) 0%, rgb(238, 171, 255) 100%);
  z-index: 999;
}

/* page transition のための設定 */
.page-container {
  padding-top: 50px;
  width: 100%;
  min-height: 100vh;
  transform-origin: 50% calc(50vh + var(--scrollY));
}
</style>

<script>
import Btn from '~/components/Btn.vue'

export default {
  components: {
    Btn,
  },
  data () {
    return {}
  },
  methods: {
    handleScroll () {
      this.setPropertyScrollY()
    },
    setPropertyScrollY () {
      (document.body || document.documentElement).style.setProperty('--scrollY', `${window.scrollY}px`)
    }
  },
  created () {
    if (process.browser) {
      this.setPropertyScrollY()
      window.addEventListener('scroll', this.handleScroll)
    }
  },
  destroyed () {
    if (process.browser) {
      window.removeEventListener('scroll', this.handleScroll)
    }
  }
}

</script>
