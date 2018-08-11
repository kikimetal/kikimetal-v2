<template>
  <!-- <section class="container"> -->
  <section>
    <div>

      <Heading title="KIKIMETAL" subtitle="kikimetal.com ver2 with Nuxt." />

      <div class="">
        <router-link :to="{ path: '/', params: {} }" exact><Btn text="home"></Btn></router-link>
        <router-link :to="{ path: '/website', params: {} }" exact><Btn text="website"></Btn></router-link>
      </div>


    </div>
  </section>
</template>

<script>
import Heading from '~/components/Heading.vue'
import Btn from '~/components/Btn.vue'

export default {
  components: {
    Heading,
    Btn,
  }
}
</script>

<style>
</style>
