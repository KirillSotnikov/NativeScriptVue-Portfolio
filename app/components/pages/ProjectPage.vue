<template>
  <Page>
    <ActionBar :title="item.name">
      <ActionItem @tap="closeWeb"
      v-show="openedWeb"
      ios.systemIcon="1"
      android.systemIcon="ic_menu_close_clear_cancel" />
    </ActionBar>
    <StackLayout v-if="!openedWeb" orientation="vertical" width="100%" height="100%"
        backgroundColor="white">
        <Image
          class="page-image"
            :src="item.imageSrc" />
        <Label :text="item.description" class="h4 text-left page-title">
        </Label>
        <Button text="Open Web" @tap="openWeb" />
    </StackLayout>
    <StackLayout v-if="openedWeb" orientation="vertical" width="100%" height="100%"
        backgroundColor="white">
        <WebViewComponent :activeSrc="item.appLink"/>
    </StackLayout>
  </Page>
</template>

<script>
  import WebViewComponent from '../common/WebViewComponent'
export default {
  props: [
    'item'
  ],
  components: {
    WebViewComponent
  },
  data () {
    return {
      openedWeb: false
    }
  },
  methods: {
    openWeb () {
      this.openedWeb = true
    },
    closeWeb () {
      this.openedWeb = false
      alert(this.openedWeb)
    }
  }
}
</script>

<style scoped>
.page-image{
  margin-bottom: 30px;
}
</style>