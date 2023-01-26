<script>
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  // components: { HelloWorld },
  data(){
    return{
      mv:"works",
    }
  },
  mounted(){
    console.log('home mounted')
  },
  methods:{
    navSwitch(e){
      if(e==1){
        this.mv="works"
      }else if(e==2){
        this.mv="git"
      }
    }
  },
}
</script>
<template>
  <div class="bg">
    <div class="cont">
      <!-- 全画面表示 アクセス時アニメーション ----------------------------------------------->
      <div class="intro">
        masashi yasaka
      </div>
      <!-- 全画面表示 アクセス時アニメーション ----------------------------------------------->
      <div class="header">
        <h1>yskms</h1>
        <nav>
          <p @click="navSwitch(1)">works</p>
          <p @click="navSwitch(2)">git</p>
        </nav>
      </div>
      <div class="main">
        <div class="works_cont" v-if="mv=='works'">
          <div>works</div>
          <div>works</div>
          <div>works</div>
        </div>
        <div class="git_cont" v-else-if="mv=='git'">
          <p>git</p>
          <a href="https://github.com/yskms">https://github.com/yskms</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bg{
  background-color: blueviolet;
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
}
.header nav{
  display: flex;
  justify-content: space-around;
}
/* ------------------------ */
.main{
  animation-name:headerAnime;
  animation-duration:6s;
  animation-fill-mode: forwards;
  opacity:0;
  color: #ffffff;
}
.works_cont{
  display: grid;
  grid-template-columns: 1fr 1fr ;
}
</style>