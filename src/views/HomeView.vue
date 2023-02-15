<script>
import AppDetail from '@/components/AppDetail.vue'

export default {
  name: 'HomeView',
  components: { AppDetail },
  data(){
    return{
      mv:true,
      isAppDetail:false,
      detailNumber:null,
    }
  },
  mounted(){
    console.log('home mounted')
  },
  methods:{
    navSwitch(e){
      if(e==1){
        this.mv=true
      }else if(e==2){
        this.mv=false
      }
    },
    openAppDetail(n){
      this.detailNumber=n
      this.isAppDetail=true
    },
    closeAppDetail(){
      this.isAppDetail=false
    },
    moveLink(url) {
      window.open(url, '_blank')
    },
  },
}
</script>
<template>
  <div class="bg">
    <div class="cont">
      <!-- 全画面表示 ----------------------------------------------->
      <!-- アクセス時アニメーション ------------------>
      <div class="intro">
        masashi yasaka
      </div>
      <!------------------------------------------>
      <!-- アプリの説明コンポーネント ----------------->
      <div class="detail" v-show="isAppDetail">
        <AppDetail @close="closeAppDetail()"
                  :detailNumber="detailNumber" />
      </div>
      <!------------------------------------------>
      <!-- 全画面表示 ここまで ----------------------------------------------->
      <div class="header">
        <h1>yskms</h1>
        <nav>
          <p class="header_ttl" @click="navSwitch(1)" :class="{underline:mv}">works</p>
          <p class="header_ttl" @click="navSwitch(2)" :class="{underline:!mv}">git</p>
        </nav>
      </div>
      <div class="main">
        <div class="works_cont" v-if="mv==true">
          <div class="works_icon">
              <img @click="openAppDetail(0)" src="../assets/hakase.png" alt="">
          </div>
          <div class="works_icon">
              <img @click="openAppDetail(1)" src="../assets/rikare.svg" alt="">
          </div>
          <div class="works_icon">
              <img @click="openAppDetail(2)" src="../assets/utc.svg" alt="">
          </div>
          <div class="works_icon">
              <img @click="openAppDetail(3)" src="../assets/othello.svg" alt="">
          </div>
        </div>

        <div class="git_cont" v-else-if="mv==false">
          <a @click="moveLink('https://github.com/yskms')">https://github.com/yskms</a>
          <!-- <a href="https://github.com/yskms">https://github.com/yskms</a> -->
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
.bg{
  background-color: black;
  width: 100vw;
  height: 100vh;
}
.cont{
  max-width: 375px;
  margin: 0 auto;
  height: 100vh;
  background-color: black;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  /* align-items: center; */
  gap: 2rem;
  /* mix-blend-mode: color-burn; */
  position: relative;
}
.detail{
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: 1;
}
/* アクセス時アニメーション --------------------------------------------*/
.intro{
  position: absolute;
  top: 45%;
  width: 100%;
  color: #ffffff;
  font-weight: bold;
  font-style: italic;
  font-size: 30px;
  animation-name:introAnime;
  animation-duration:3s;
  animation-fill-mode: forwards;
  opacity:0;
  text-shadow: 2px 3px 3px rgba(0, 0, 0, 0.2);
}
@keyframes introAnime{
  0% {opacity: 0;}
  20% {opacity: 1;transform: translateX(0);}
  50% {opacity: 0.9;transform: translateX(0);}
  80% {opacity: 0;transform: translateX(0);}
}
.header{
  animation-name:headerAnime;
  animation-duration:6s;
  animation-fill-mode: forwards;
  opacity:0;
  color: #ffffff;
  width: 100%;
  height: 15%;
}
@keyframes headerAnime{
  0% {opacity: 0;  }
  35% {opacity: 0;transform: translateX(0);}
  55% {opacity: 1;transform: translateX(0);}
  100% {opacity: 1;transform: translateX(0);}
}
/* アクセス時アニメーション ここまで--------------------------------------------*/
.header h1{
  text-align: left;
  padding-left: 0.1em;

}
.header nav{
  display: flex;
  justify-content: space-around;
}
.header_ttl{
  transition: 0.5s;
}
.header_ttl:hover{
  transform: scale(1.2);
}
.underline{
  border-bottom: solid white 1px;
}
/* ------------------------ */
.main{
  animation-name:headerAnime;
  animation-duration:6s;
  animation-fill-mode: forwards;
  opacity:0;
  color: #ffffff;
  height: 85%;
  width: 100%;
}
.works_cont{
  height: 80%;
  width: 90%;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr ;
}
.works_icon{
  width: 100%;
  padding: 35%;
}
.works_icon img{
  width: 100%;
  transition: 0.5s;
}
.works_icon img:hover{
  transform: scale(1.2);
}

.git_cont{
  cursor: pointer;
  transition: 0.5s;
}
.git_cont:hover{
  transform: scale(1.1);
}
</style>