<template>
<AbsoluteLayout>
    <StackLayout v-if="!openedWeb" left="0" top="0" orientation="vertical" width="100%" height="100%"
        backgroundColor="white">
        <Label text="Projects List" class="h2 text-left page-title">
        </Label>
        <ListView for="portfolioItem in portfolioList" 
            @itemTap="onItemTap"
            style="height:100%"
          >
            <v-template>
                <FlexboxLayout flexDirection="row">
                    <Image :src="portfolioItem.imageSrc"
                        class="thumb img-circle" />
                    <Label :text="portfolioItem.name" class="t-12"
                        style="width: 60%" />
                </FlexboxLayout>
            </v-template>
        </ListView>
    </StackLayout>
    <WebViewComponent 
      :closeFunc="closeWeb" 
      v-else left="0" 
      top="0" 
      width="100%" 
      height="100%" 
      :activeSrc="activeSrc"
    />
</AbsoluteLayout>
</template>

<script>
import WebViewComponent from '../common/WebViewComponent'
    export default {
      components: {
        WebViewComponent
      },
        methods: {
            onItemTap: function(args) {
              this.activeSrc = args.item.appLink
              this.openWeb()
            },
            
            openWeb () {
              this.openedWeb = true
            },

            closeWeb () {
              this.openedWeb = false
            }
        },

        data() {
            return {
              openedWeb: false,
              activeSrc: null,
              portfolioList: [{
                    name: "Shkola Kevin",
                    imageSrc: "https://instagram.fods3-1.fna.fbcdn.net/v/t51.2885-19/s150x150/93780361_669715910525606_743286258561712128_n.jpg?_nc_ht=instagram.fods3-1.fna.fbcdn.net&_nc_ohc=50wWMtUO4k0AX8FPo-c&oh=c8d1125e536dba80732b9e5ed65270af&oe=5ED41C0E",
                    appLink: "https://shkolakevin.com.ua/"
                  },
                  {
                      name: "Art-Point",
                      imageSrc: "https://scontent.fods3-1.fna.fbcdn.net/v/t31.0-0/p370x247/14713023_1654872208176497_2138925450030951711_o.jpg?_nc_cat=106&_nc_sid=85a577&_nc_ohc=_3n9eYSEUroAX98eg4j&_nc_ht=scontent.fods3-1.fna&_nc_tp=6&oh=58cc7eb2ed5245833eed7a70c01a94bd&oe=5ECD5AFF",
                      appLink: "http://art-point.net/"
                  },
                  {
                      name: "Flaim Models",
                      imageSrc: "https://instagram.fods3-1.fna.fbcdn.net/v/t51.2885-19/s150x150/90863390_572121460322686_1389936689266294784_n.jpg?_nc_ht=instagram.fods3-1.fna.fbcdn.net&_nc_ohc=ngX_81gfFCgAX8iyM3D&oh=f572e0e6336d4aeb5e4d9f58eef324f8&oe=5ED03E53",
                      appLink: "http://flaimmodels.com/"
                  }
              ]
            };
        }
    };
</script>

<style scoped>
    .page-title {
        padding-top: 20px;
        padding-left: 20px;
    }
</style>