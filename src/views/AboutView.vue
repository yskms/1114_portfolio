<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'AboutView',
  // components: {
  //   HelloWorld
  // }
}
</script>

<template>
<div class="cont">
  <div class="main">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div id="left_box">
      <div class="left_fill">
        <div class="left_fill_inside"></div>
      </div>
    </div>
    <!--left_box-->

    <div class="list">
      <div class="list_main">
        <h2>portfolio</h2>
      </div>
    </div>

    <div class="logo">
      <div class="logo_main"></div>
    </div>

    <div id="right_box">
      <div class="right_fill">
        <div class="right_fill_inside"></div>
      </div>
    </div>
    <!--right_box-->
  </div>
  </div>
</template>

<style scoped>
.cont{
  background-color: grey;
}
.main{
  background-color: black;
  display: grid;
  max-width: 1200px;
  grid-template-columns: 1fr 5fr 5fr 1fr;
}
.list{
  width: 400px;
  background-color: yellowgreen
}
.list_main{
  width: 80%;
  margin: 0 auto;
  background-color: black;
}
.logo{
  position: relative;
}
@keyframes border-animation {
  to { transform: rotate(360deg); }
}
.logo_main{
  position: absolute;
  top: 0;
  left: 0;
  /* border-radius: 50%; */
  border-radius: 50% 50% 50% 70%/50% 50% 70% 60%;
  animation: border-animation 50s infinite linear;



  --c1: red;
  --c2: orange;
  --c3: yellow;
  --c4: green;
  --c5: blue;
  --c6: indigo;
  --c7: violet;
  
  --solid: var(--c1), var(--c2), var(--c3), var(--c4), var(--c5), var(--c6), var(--c7);
  --solid-wrap: var(--solid), var(--c1);
  --trans: 
    var(--c1), transparent,
    var(--c2), transparent,
    var(--c3), transparent,
    var(--c4), transparent,
    var(--c5), transparent,
    var(--c6), transparent,
    var(--c7)
  ;
  --trans-wrap: var(--trans), transparent, var(--c1);
  
  background: 
    radial-gradient(circle, var(--trans)),
    conic-gradient(from 180deg, var(--trans-wrap)),
    radial-gradient(circle, var(--trans)),
    conic-gradient(var(--solid-wrap));
  background-blend-mode: overlay;
  height: 500px;
  width: 450px;
}



#left_box {
  position: relative; /* ::beforeで作るレイヤーの基準点 */
  width: 50px;/* 画面の横幅いっぱい */
  height: 100vh;
  overflow: hidden;
  margin: 5%;
}

/* ブロックの下にレイヤーを追加して背景にストライプを描く */
#left_box::after {
  content: "";/* 空の入れ物（レイヤー）を作る */
  display: block;
  width: 50px;/* 画面の横幅いっぱい */
  height: 70vh;  /* 画面の高さいっぱい */
  position: absolute; /* 強制的に親のtop:0, left:0;にポジション */
  /* z-index: -1;レイヤーの下に */
  background-color: yellow;
  /* background: repeating-linear-gradient(135deg,#f6578f 0,#f6578f 4px,#fbaac7 4px,#fbaac7 8px); */
  transform: skewY(329deg); /* レイヤーを台形に変形 */
  transform-origin: bottom right;/* 台形に変形する際の基準点 */
}
.left_fill{
  width: 25px;
  height: 60vh;
  /* background-color: black; */
  position: absolute;
  top: 17vh;
  right: 0;
}
.left_fill_inside{
  position: relative;
}
.left_fill_inside::after {
  content: "";/* 空の入れ物（レイヤー）を作る */
  display: block;
  width: 50px;/* 画面の横幅いっぱい */
  height: 40vh;  /* 画面の高さいっぱい */
  position: absolute; /* 強制的に親のtop:0, left:0;にポジション */
  z-index: 1;
  background-color: black;
  /* background: repeating-linear-gradient(135deg,#f6578f 0,#f6578f 4px,#fbaac7 4px,#fbaac7 8px); */
  transform: skewY(329deg); /* レイヤーを台形に変形 */
  transform-origin: bottom right;/* 台形に変形する際の基準点 */
}



#right_box {
  position: relative; /* ::beforeで作るレイヤーの基準点 */
  width: 50px;/* 画面の横幅いっぱい */
  height: 100vh;
  overflow: hidden;
  margin: 5%;
}

/* ブロックの下にレイヤーを追加して背景にストライプを描く */
#right_box::after {
  content: "";/* 空の入れ物（レイヤー）を作る */
  display: block;
  width: 50px;/* 画面の横幅いっぱい */
  height: 73vh;  /* 画面の高さいっぱい */
  position: absolute; /* 強制的に親のtop:0, left:0;にポジション */
  /* z-index: -1;レイヤーの下に */
  background-color: yellow;
  /* background: repeating-linear-gradient(135deg,#f6578f 0,#f6578f 4px,#fbaac7 4px,#fbaac7 8px); */
  transform: skewY(329deg); /* レイヤーを台形に変形 */
  transform-origin: top left;/* 台形に変形する際の基準点 */
}
.right_fill{
  width: 25px;
  height: 60vh;
  /* background-color: black; */
  position: absolute;
  top: 0vh;
  left: 0;
  overflow: hidden;
}
.right_fill_inside{
  position: relative;
  /* width: 100%; */
}
.right_fill_inside::after {
  content: "";/* 空の入れ物（レイヤー）を作る */
  display: block;
  width: 5vw;/* 画面の横幅いっぱい */
  height: 40vh;  /* 画面の高さいっぱい */
  position: absolute; /* 強制的に親のtop:0, left:0;にポジション */
  z-index: 1;
  background-color: black;
  /* background: repeating-linear-gradient(135deg,#f6578f 0,#f6578f 4px,#fbaac7 4px,#fbaac7 8px); */
  transform: skewY(329deg); /* レイヤーを台形に変形 */
  transform-origin: top left;/* 台形に変形する際の基準点 */
}
</style>
