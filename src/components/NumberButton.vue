<template>
  <div class="button">
    {{buttonIndex}}
    {{buttonString}}
  </div>
</template>
<script>
export default {
  props: {
    buttonIndex: Number,
    buttonString: String
  }
}
</script>
<style>
.button{
  width: 100px;
}
</style>