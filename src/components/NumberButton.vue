<template>
  <div class="button" :style="buttonSize" @click="pushClickInfo">
    {{buttonNumber}}{{buttonString}}
  </div>
</template>
<script>
export default {
  mounted(){
    if(this.buttonNumber===0){
      this.buttonSize = {
        width: '320px'
      };
    }
  },
  data() {
    return {
      buttonSize: {
        width: '100px'
      },
    }
  },
  methods: {
    pushClickInfo() {
      if(this.buttonType=="Number" )
        this.$parent.numSet(this.buttonNumber);
      else
        this.$parent.calculateMiddle(this.buttonString);
    }
  },
  props: {
    buttonNumber: Number,
    buttonString: String,
    buttonType: String
  }
}
</script>
<style lang="scss" scoped>
.button{
  background-color: #f0f0f0;
  margin: 5px;
  border-radius: 20px;
  width: 100px;
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