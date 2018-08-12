<template lang="html">
  <div class="Btn" :style="style">
    {{ text }}
  </div>
</template>

<script>
export default {
  props: ["text", "bg"],
  data () {
    return {
      style: this.bg ? {background: this.bg} : {}
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
  text-shadow: 0 1px 8px rgba(50, 0, 30, 0.2);
  border-radius: 0.3em;
}
</style>
