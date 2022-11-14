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
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div id="left_box">
      <div class="left_fill">
        <div class="left_fill_inside"></div>
      </div>
    </div>
    <!--box-->
  </div>
</template>

<style scoped>
.home{
  background-color: black;
}
#left_box {
  position: relative; /* ::beforeで作るレイヤーの基準点 */
  width: 10vw;/* 画面の横幅いっぱい */
  height: 100vh;
  overflow: hidden;
}

/* ブロックの下にレイヤーを追加して背景にストライプを描く */
#left_box::after {
  content: "";/* 空の入れ物（レイヤー）を作る */
  display: block;
  width: 10vw;/* 画面の横幅いっぱい */
  height: 70vh;  /* 画面の高さいっぱい */
  position: absolute; /* 強制的に親のtop:0, left:0;にポジション */
  /* z-index: -1;レイヤーの下に */
  background: repeating-linear-gradient(135deg,#f6578f 0,#f6578f 4px,#fbaac7 4px,#fbaac7 8px);
  transform: skewY(329deg); /* レイヤーを台形に変形 */
  transform-origin: bottom right;/* 台形に変形する際の基準点 */
}
.left_fill{
  width: 5vw;
  height: 60vh;
  /* background-color: black; */
  position: absolute;
  top: -5vh;
  right: 0;
}
.left_fill_inside{
  position: relative;
}
.left_fill_inside::after {
  content: "";/* 空の入れ物（レイヤー）を作る */
  display: block;
  width: 10vw;/* 画面の横幅いっぱい */
  height: 60vh;  /* 画面の高さいっぱい */
  position: absolute; /* 強制的に親のtop:0, left:0;にポジション */
  z-index: 1;
  background-color: black;
  /* background: repeating-linear-gradient(135deg,#f6578f 0,#f6578f 4px,#fbaac7 4px,#fbaac7 8px); */
  transform: skewY(329deg); /* レイヤーを台形に変形 */
  transform-origin: bottom right;/* 台形に変形する際の基準点 */
}
</style>