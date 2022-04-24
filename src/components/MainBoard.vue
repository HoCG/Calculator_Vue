<template>
  <div class="main-board">
    <div class="board-part">
      <CalculateViewer :calculate="calculate"></CalculateViewer>
    </div>
    <div class="result-part"></div>
    <div class="button-part">
      <div class="number-part">
        <div class="board-part">
          <NumberButton v-for="buttonNumber in buttonTotal" :key="buttonNumber" :buttonIndex="buttonNumber"></NumberButton>
        </div>
        <div class="board-part">
          <NumberButton v-for="buttonNumber in buttonTotal" :key="buttonNumber+3" :buttonIndex="buttonNumber+3"></NumberButton>
        </div>
        <div class="board-part">
          <NumberButton v-for="buttonNumber in buttonTotal" :key="buttonNumber+6" :buttonIndex="buttonNumber+6"></NumberButton>
        </div>
        <NumberButton :buttonIndex="0"></NumberButton>
      </div>
      <div class="side-calculate-part">
        <NumberButton v-for="buttonString in calculateButtonString" :key="buttonString" :buttonString="buttonString"></NumberButton>
      </div>
    </div>
  </div>
</template>
<script>
import NumberButton from './NumberButton.vue';
import CalculateViewer from './CalculateViewer.vue';

export default {
  data() {
    return{
      calculate: ' ',
      buttonTotal: 3,
      calculateButtonString: ['+', '*', '-', '/']
    }
  },
  components: {
    NumberButton,
    CalculateViewer
  }
}
</script>
<style lang="scss" scoped>
.button-part{
  display: flex;
  justify-content: center;
  //flex-direction: column;
}
.main-board{
  display: flex;
  justify-content: center;
  flex-direction: column;
  background-color: #c0c0c0;
  border-radius: 20px;
  width: 500px;
  height: 50%;
}
.board-part{
  display: flex;
  justify-content: space-around;
}
.push-part{
  display: flex;
  justify-content: center;
}
.side-calculate-part{
  div{
    margin-bottom: 10px;
  }
}
</style>