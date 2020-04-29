<template>
  <StackLayout orientation="vertical" width="100%" height="100%"
      backgroundColor="white">
      <Label text="My Portfolio projects" class="h3 text-left page-title">
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
</template>

<script>
import ProjectPage from './ProjectPage'
    export default {
        methods: {
            onItemTap (args) {
              this.$navigateTo(ProjectPage, {
                transition: {},
                transitioniOS: {},
                transitionAndroid: {},
                props: {
                  item: args.item,
                }
              })
            }
        },

        data() {
            return {
              page: ProjectPage,
              portfolioList: [
                {
                  name: "Dental Center",
                  description: "Dental Center Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://cdn0.iconfinder.com/data/icons/medical-and-health-37/32/Icon9-teeth-512.png",
                  appLink: "http://kirill.comnd-x.com/dental/dist/index.html"
                },
                {
                  name: "StartUp University",
                  description: "StartUp University Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://cdn.iconscout.com/icon/free/png-256/startup-30-285613.png",
                  appLink: "http://startup.comnd-x.com/"
                },
                {
                  name: "Современный дом",
                  description: "Современный дом Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://modernhouse.od.ua/img/logo.png",
                  appLink: "https://modernhouse.od.ua/"
                },
                {
                  name: "Театр квестов",
                  description: "Театр квестов Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://scontent.fods3-1.fna.fbcdn.net/v/t1.0-1/p200x200/64318503_2069776993328010_6285509780987445248_n.png?_nc_cat=109&_nc_sid=dbb9e7&_nc_ohc=2Zdi-xnbizwAX_r_E0B&_nc_ht=scontent.fods3-1.fna&oh=62c9b2066495d5fccb4cf41db90fd190&oe=5ED033E6",
                  appLink: "https://www.teatrquest.com/"
                },
                {
                  name: "Pride Logistics",
                  description: "Pride Logistics Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://www.seekpng.com/png/detail/2-27923_this-free-icons-png-design-of-golden-lion.png",
                  appLink: "https://pride-logistika.com/"
                },
                {
                  name: "ЕЦКР",
                  description: "ЕЦКР Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://kadastrovye-raboty.mosuyrist.ru/wp-content/uploads/2019/07/ikonka-Kadastrovye-i-geodezicheskie-raboty-174x177.png",
                  appLink: "http://kirill.comnd-x.com/eckr/dist/"
                },
                {
                  name: "Vlady Design",
                  description: "Vlady Design Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://vladydesign.com/img/logo_vladi.png",
                  appLink: "https://vladydesign.com/"
                },
                {
                  name: "First Step",
                  description: "First Step Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f2/Flag_of_Great_Britain_%281707%E2%80%931800%29.svg/1000px-Flag_of_Great_Britain_%281707%E2%80%931800%29.svg.png",
                  appLink: "http://www.the-first-step.com.ua/"
                },
                {
                  name: "Skin Care Laser",
                  description: "Skin Care Laser Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://image.flaticon.com/icons/png/512/971/971558.png",
                  appLink: "http://skincarelaser.ca/"
                },
                {
                  name: "Clean Saskatoon",
                  description: "Clean Saskatoon Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://icons.iconarchive.com/icons/blackvariant/button-ui-requests-2/1024/CleanMyMac-1-icon.png",
                  appLink: "https://cleansaskatoon.ca/"
                },
                {
                  name: "Best Auto",
                  description: "Best Auto Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://lh3.googleusercontent.com/proxy/SvNjnhRRSJCT6cTJu_JPUaobWlNgWsPcndq5ioFp2dt8pqZITz79JS3mqeZt1fmfu87KCbXLbW-178VgG6aDNJCcmAKTrPTqDHmuDHA2AWc0LSeo1F0ArhkaMyqxqcAxwaMqIutKaB4ys6seZNWwd_zmBDMJ",
                  appLink: "http://best-auto.comnd-x.com/login"
                },
                {
                  name: "Shkola Kevin",
                  description: "Shkola Kevin Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://instagram.fods3-1.fna.fbcdn.net/v/t51.2885-19/s150x150/93780361_669715910525606_743286258561712128_n.jpg?_nc_ht=instagram.fods3-1.fna.fbcdn.net&_nc_ohc=50wWMtUO4k0AX8FPo-c&oh=c8d1125e536dba80732b9e5ed65270af&oe=5ED41C0E",
                  appLink: "https://shkolakevin.com.ua/"
                },
                {
                  name: "Art-Point",
                  description: " Art-Point Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
                  imageSrc: "https://scontent.fods3-1.fna.fbcdn.net/v/t31.0-0/p370x247/14713023_1654872208176497_2138925450030951711_o.jpg?_nc_cat=106&_nc_sid=85a577&_nc_ohc=_3n9eYSEUroAX98eg4j&_nc_ht=scontent.fods3-1.fna&_nc_tp=6&oh=58cc7eb2ed5245833eed7a70c01a94bd&oe=5ECD5AFF",
                  appLink: "http://art-point.net/"
                },
                {
                  name: "Flaim Models",
                  description: "Flaim Models Project Description. But now - it's Lorem :( Flaim Models Project Description. But now - it's Lorem :(  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae at deserunt doloribus atque corporis accusamus voluptates voluptate fugiat voluptatum esse numquam labore quod dolor, hic itaque, rerum, quaerat velit nihil.",
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