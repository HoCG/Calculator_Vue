<template>
  <div class="calculate-viewer">
    {{calculate}}
  </div>
</template>
<script>
export default {
  props: {
    calculate: String
  }
}
</script>
<style>
.calculate-viewer{
  margin: 10px;
  width: 80%;
  height: 80px;
  background-color: white;
}
</style>