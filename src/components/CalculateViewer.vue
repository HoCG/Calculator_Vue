<template>
  <div class="calculate-viewer">
    {{input}}
  </div>
</template>
<script>
export default {
  props: {
    input: String
  }
}
</script>
<style>
.calculate-viewer{
  margin: 10px;
  width: 80%;
  height: 80px;
  background-color: white;
  text-align: center;
  justify-content: center;
}
</style>