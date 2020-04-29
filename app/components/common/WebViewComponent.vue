<template>
  <WebView left="0" top="0" width="100%" height="100%" :src="activeSrc" />
</template>

<script>
export default {
  props: [
    'activeSrc',
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