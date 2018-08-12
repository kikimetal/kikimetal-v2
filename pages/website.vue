<template>
  <section class="page-container">
    <div>
      <Heading title="WEBSITE" subtitle="kikimetal.com ver2 with Nuxt." />

      <div>
        <Btn text="GETT!!!!" bg="pink" />
      </div>

      <div v-for="(row, index) in sheet" :key="index + row.date">
        <Heading :title="row.date" :subtitle="row['main-title-01']" />
      </div>

      <div v-for="(site, index) in sites" :key="index + site.date">
        <Heading :title="site.title" :subtitle="index" />
      </div>

    </div>
  </section>
</template>

<script>
import Btn from '~/components/Btn.vue'
import Heading from '~/components/Heading.vue'

import sites from '~/assets/websites.json'

import axios from "axios"

export default {
  components: {
    Btn,
    Heading,
  },
  data () {
    return {
      sites,
      sheet: [],
      url: "https://www.maylily.co.jp/v2/assets/gss-api.php?sheetName=news&date&main-title-01&main-title-02&sub-title&description&img-src&img-alt&link-flg&link-text&link-href",
    }
  },
  methods: {
    async getSheet () {
      let res = await axios.get("https://www.maylily.co.jp/v2/assets/gss-api.php?sheetName=news&date&main-title-01&main-title-02&sub-title&description&img-src&img-alt&link-flg&link-text&link-href")
      if (!res.status === 200) {
        throw new Error(res.statusText)
      }
      this.sheet = res.data
    },
  },
  created () {
    if (process.browser) {
      this.getSheet()
    }
  },
}


</script>

<style>

</style>
