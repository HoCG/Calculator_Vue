<template>
  <div class="main-view">
    <MainBoard></MainBoard>
  </div>
</template>
<script>
import MainBoard from "../components/MainBoard.vue"
export default {
  components: {
    MainBoard
  }
}
</script>
<style scoped>
.main-view{
  display: flex;
  justify-content: center;
  width: 100%;
  font-size: 20px;
  font-weight: 600;
  height: 100%;
}
</style>