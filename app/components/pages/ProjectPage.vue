<template>
  <Page>
    <ActionBar :title="item.name">
      <NavigationButton v-show="!openedWeb" text="Go back" android.systemIcon="ic_menu_back" @tap="$navigateBack" />
      <ActionItem @tap="closeWeb"
      v-show="openedWeb"
      class="action-item"
      ios.systemIcon="1"
      android.systemIcon="ic_menu_close_clear_cancel" />
    </ActionBar>

    <ScrollView v-if="!openedWeb" orientation="vertical">
      <StackLayout  orientation="vertical" width="100%"
          backgroundColor="white">
          <Image
            class="page-image"
            :src="item.imageSrc" />
          <Label :text="item.name" class="h2 text-center page-title"/>
          <TextView editable="false" :text="item.description" class="h4 text-left" />
          <Button text="Open Web" @tap="openWeb" />
          <Button class="back-button" text="Go Back" @tap="$navigateBack" />
      </StackLayout >
    </ScrollView>

    <StackLayout v-else orientation="vertical" width="100%" height="100%"
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
    }
  }
}
</script>

<style scoped>
.page-image{
  margin-bottom: 30px;
}
.back-button{
  background-color: #34495e;
  color: #ffffff;
}
.action-item{
  color: #34495e;
}
</style>