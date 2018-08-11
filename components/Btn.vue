<template lang="html">
  <div class="Btn">
    {{ text }}
  </div>
</template>

<script>
export default {
  props: ["text"],
}
</script>

<style lang="css">
.Btn{
  font-size: 22px;
  padding: 1em 2em;
  background: grey;
  color: white;
  border-radius: 5px;
}
</style>
