<template>
  <section class="page-container">
    <div>

      <Heading title="KIKIMETAL" subtitle="kikimetal.com ver2 with Nuxt." />

      <h1>LazyLoadImg</h1>
      <LazyLoadImg filename="kikigirl.jpg"/>
      <LazyLoadImg filename="kikigirl.jpg"/>
      <LazyLoadImg filename="kikigirl.jpg"/>

      <h1>Normal</h1>
      <!-- <img src="~/assets/img/kikigirl.jpg" alt="ききるんのイラスト" /> -->


      <div class="">
        <router-link :to="{ path: '/', params: {} }" exact><Btn text="home"></Btn></router-link>
        <router-link :to="{ path: '/website', params: {} }" exact><Btn text="website"></Btn></router-link>
      </div>

    </div>
  </section>
</template>

<script>
// import VueProgressiveImage from 'vue-progressive-image'
import Heading from '~/components/Heading.vue'
import Btn from '~/components/Btn.vue'
import LazyLoadImg from '~/components/LazyLoadImg.vue'

export default {
  components: {
    Heading,
    Btn,
    LazyLoadImg,
  }
}
</script>

<style>
</style>
