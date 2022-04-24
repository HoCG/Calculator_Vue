<template>
  <div v-if="buttonString=='AC'" class="button">
    AC
  </div>
  <div v-else class="button">
    Enter
  </div>
</template>
<script>
export default {
  data() {
    return {
      buttonSize: {
        width: '100px'
      },
    }
  },
  props: {
    buttonString: String
  }
}
</script>
<style lang="scss" scoped>
.button{
  background-color: #f0f0f0;
  margin: 5px;
  border-radius: 20px;
  width: 210px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer; 
  &:hover{
    transition-duration: 0.2s;
    // background-color: #d5d5d5;
    box-shadow:inset 3px 3px 3px 3px #000000;
  }

  &:active{
  transition-duration: 0.1s;
  // background-color: #d5d5d5;
  box-shadow:inset 5px 5px 5px 5px #000000;
  }
}
</style>