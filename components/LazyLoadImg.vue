<template lang="html">
  <div class="LazyLoadImg" :style="{ backgroundImage: 'url(' + require('~/assets/img/' + filename) + ')' }">
    <div class="LazyLoadImg__placeholder" :class="{loaded: isLoaded}"><img class="loader" src="~/assets/img/loading.svg" alt="" /></div>
    <img class="LazyLoadImg__fake" :src="require('~/assets/img/' + filename)" @load="loaded"/>
  </div>
</template>

<script>
export default {
  props: [
    "filename"
  ],
  data () {
    return {
      isLoaded: false,
    }
  },
  methods: {
    loaded () {
      console.log("Loaded!!")
      this.isLoaded = true
      console.log(this.isLoaded)
    }
  }
}
</script>

<style lang="scss">
.LazyLoadImg{
  position: relative;
  width: 100%;
  padding-top: 100%;
  height: 0;
  overflow: hidden;

  background-color: grey;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;

  &__placeholder{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;

    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    background: white;

    user-select: none;
    pointer-events: none;
    transition: all 0.4s ease 0.7s;

    &.loaded{
      transform: scale(1.3);
      opacity: 0;
    }

    .loader{
      width: 100px;
      height: auto;
    }
  }

  &__fake{
    display: none;
  }

}
</style>
