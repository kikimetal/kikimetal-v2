<template lang="html">
  <div class="Btn" :style="overrideStyle">
    {{ text }}
  </div>
</template>

<script>
export default {
  props: ["text", "overrideStyle"],
  data () {
    return {
      // style: this.bg ? {background: this.bg} : {}
      // style: thisstyle
    }
  },

}
</script>

<style lang="css">
.Btn{
  font-size: 20px;
  padding: 0.5em 1.4em;
  background: rgba(255,255,255,0.2);
  color: white;
  border-radius: 0.3em;
  box-shadow: 0 5px 15px 0 rgba(46,61,73,.1);
}
</style>
