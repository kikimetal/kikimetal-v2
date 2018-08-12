<template>
  <section class="page-container">
    <div>

      <Logotype fill="pink" />
      <!-- <Heading title="KIKIMETAL" subtitle="kikimetal.com ver2 with Nuxt." /> -->

      <Heading title="LazyLoadImg" subtitle="LazyLoadImg" />
      <LazyLoadImg filename="kikigirl.jpg"/>
      <LazyLoadImg filename="kikigirl.jpg"/>
      <LazyLoadImg filename="kikigirl.jpg"/>

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
import Logotype from '~/components/Logotype.vue'

export default {
  components: {
    Heading,
    Btn,
    LazyLoadImg,
    Logotype,
  }
}
</script>

<style>
.logotype{
  fill: pink;
}
</style>
