<template>
  <div class="main-board">
    <div class="board-depth board-part">
      <CalculateViewer :input="input"></CalculateViewer>
    </div>
    <div class="board-depth result-part">
      <ActionButton :buttonString="'AC'" :input="input"></ActionButton>
      <ActionButton :buttonString="'Enter'" :input="input"></ActionButton>
    </div>
    <div class="board-depth button-part">
      <div class="number-part">
        <div class="board-part">
          <NumberButton v-for="buttonNumber in buttonTotal" :key="buttonNumber" :buttonNumber="buttonNumber" :buttonType="'Number'"></NumberButton>
        </div>
        <div class="board-part">
          <NumberButton v-for="buttonNumber in buttonTotal" :key="buttonNumber+3" :buttonNumber="buttonNumber+3" :buttonType="'Number'"></NumberButton>
        </div>
        <div class="board-part">
          <NumberButton v-for="buttonNumber in buttonTotal" :key="buttonNumber+6" :buttonNumber="buttonNumber+6" :buttonType="'Number'"></NumberButton>
        </div>
        <NumberButton :buttonNumber="0" :buttonType="'Number'"></NumberButton>
      </div>
      <div class="side-calculate-part">
        <NumberButton v-for="buttonString in calculateButtonString" :key="buttonString" :buttonString="buttonString" :buttonType="'String'"></NumberButton>
      </div>
    </div>
  </div>
</template>
<script>
import NumberButton from './NumberButton.vue';
import ActionButton from './ActionButton.vue';
import CalculateViewer from './CalculateViewer.vue';

export default {
  data() {
    //구조는 no1 calculateType no2 = result의 구조라고 보면된다.
    return  {
      no1: 0, //계산에 쓸 첫번째값
      no2: 0, //계산에 쓸 두번째값
      result: 0, //결과값
      input: '', //출력과 잠시 저장을 위한 스트링갓
      calculateType: '', //계산 형태를 정하기 위한 스트링값
      buttonTotal: 3,
      calculateButtonString: ['+', '*', '-', '/']
    }
  },
  components: {
    NumberButton,
    CalculateViewer,
    ActionButton
  },
  methods: {
    resetCalculate(){
      this.input = "";
    },
    numSet(number){
      this.input += String(number);
    },
    calculateMiddle(buttonString){
      this.calculateType = buttonString; //계산 형태를 지정하고
      this.no1 = Number(this.input) + this.result;
      this.input = "";
    },
    showResult(){
      this.no2 = Number(this.input);
      if(this.calculateType == "+"){
        this.result = this.no1 + this.no2;
      }
      else if(this.calculateType == "-"){
        this.result = this.no1 - this.no2;
      }
      else if(this.calculateType == "*"){
        this.result = this.no1 * this.no2;
      }
      else if(this.calculateType == "/"){
        this.result = this.no1 / this.no2;
      }
      this.no1 = this.result;
      this.input = String(this.result);
      this.result = 0;
    }
  }
}
</script>
<style lang="scss" scoped>
.result-part{

}
.main-board{
  display: flex;
  justify-content: center;
  flex-direction: column;
  background-color: #c0c0c0;
  border-radius: 20px;
  width: 500px;
  height: 50%;
  .board-depth{
    display: flex;
    justify-content: center;
  }
}
.board-part{
  display: flex;
  justify-content: space-around;
}
.side-calculate-part{
  div{
    margin-bottom: 10px;
  }
}
</style>