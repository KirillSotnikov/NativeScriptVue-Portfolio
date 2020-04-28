<template>
<AbsoluteLayout>
  <WebView left="0" top="0" width="100%" height="100%" :src="activeSrc" />
  <Button class="bottom-button" left="-25px" top="250px" width="100px" height="100px" text="X" @tap="closeFunc" />
</AbsoluteLayout>
</template>

<script>
export default {
  props: [
    'activeSrc',
    'closeFunc'
  ]
}
</script>

<style scoped>
.bottom-button{
  background-color: rgba(255, 255, 255, 0.8);
  color: #313131;
  border: 1px solid #313131;
  border-radius: 5px;
}
</style>