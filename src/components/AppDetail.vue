<script>
export default {
  name: 'AppDetail',
  props: ['detailNumber',],
  data(){
    return{
      screenshotArr:[
        "img/hakase_ss.png",
        "img/rikare_ss.png",
        "img/utc_ss.png",
        "img/othello_ss.png",],
      iconArr:[
        "img/hakase.png",
        "img/rikare.svg",
        "img/utc.svg",
        "img/othello.svg",],
      titleArr:[
        "国旗ハカセ",
        "リカレめし",
        "UTC NOW",
        "VanillaJS-オセロ"],
      urlArr:[
        "https://remarkable-salmiakki-887cba.netlify.app/",
        "https://deft-toffee-382a3f.netlify.app/",
        "https://chic-lebkuchen-daab8b.netlify.app/",
        "https://voluble-macaron-a9260e.netlify.app/",],
      qrArr:[
        "img/hakase_qr.png",
        "img/rikare_qr.png",
        "img/utc_qr.png",
        "img/othello_qr.png",],
      commentArr:[
        "国旗クイズアプリです。職業訓練中の自主制作課題で最初に作成。Firebaseを利用してAuthやランキング登録などを実装しました。Figmaでプレゼン資料も作成しました。",
        "土佐堀周辺のオススメごはん屋さんを登録するアプリです。開発スピードを意識して機能を絞り込んで作成し、2週間でほぼ完成させました。",
        "UTCの時間を表示させるだけのシンプルアプリです。日付や時間の扱いに苦労しました。デザインも悩みましたが、最終的にはシンプルにまとめました。5日で作成。",
        "VanillaJSで作成したアプリです。勉強初期に作成したので、配列で処理できるところを繰り返しで記述していたり、いたらぬ点も多いですが、デバッグやエラー処理が楽しかったです。",
      ],
      githubArr:[
        "https://github.com/yskms/1023_flag_app_v2",
        "https://github.com/yskms/1117_rikameshi.git",
        "https://github.com/yskms/1205_utc_now_v3.git",
        ”https://github.com/yskms/practice07-othello",],
      figmaArr:[
        "https://pitchdeck.hypermatic.com/slides/l9rx5yyj40410?token=VjR4biQlU2lIYmhIelo%3D",
        "",
        "",
        "",],
    }
  },
  methods:{
    moveLink(url) {
      window.open(url, '_blank')
    },
    closeWindow(){
      this.$emit('close')
    },
  },
}
</script>

<template>
  <div class="appDetail_cont">
    <div class="appDetail_main">

      <div class="screenshot">
        <img :src=screenshotArr[detailNumber] alt="">
      </div>
      
      <div class="content_wrap">
        <div class="content1">
          <div class="content1_left">
            <div class="content1_icon">
              <img :src=iconArr[detailNumber] alt="icon">
            </div>
            <p class="content1_title">{{titleArr[detailNumber]}}</p>
            <p class="content1_url">
              <a @click="moveLink(urlArr[detailNumber])">{{urlArr[detailNumber]}}</a>
            </p>
          </div>
          <div class="content1_right">
            <img :src=qrArr[detailNumber] alt="qr_code">
          </div>
        </div>
        <div class="content2">
          <p>{{commentArr[detailNumber]}}</p>
        </div>
        <div class="content3">
          <p v-show="githubArr[detailNumber]" @click="moveLink(githubArr[detailNumber])">GitHub</p>
          <p v-show="figmaArr[detailNumber]" @click="moveLink(figmaArr[detailNumber])">Figma</p>
        </div>
      </div>

      <div class="close_area">
        <svg @click="closeWindow()" xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="white" class="bi bi-x-lg" viewBox="0 0 16 16">
              <path fill-rule="evenodd" d="M13.854 2.146a.5.5 0 0 1 0 .708l-11 11a.5.5 0 0 1-.708-.708l11-11a.5.5 0 0 1 .708 0Z"/>
              <path fill-rule="evenodd" d="M2.146 2.146a.5.5 0 0 0 0 .708l11 11a.5.5 0 0 0 .708-.708l-11-11a.5.5 0 0 0-.708 0Z"/>
        </svg>
      </div>

    </div>
  </div>
</template>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.appDetail_cont{
  background-color: rgba(0, 0, 0, 0.6);
  color: aliceblue;
  height: 100%;
  width: 100%;
  /* z-index: 3; */
  padding: 5%;
  backdrop-filter: blur(1px);

}
/* --------------------------------- */
.appDetail_main{
  height: 100%;
  width: 100%;
  margin: 0 auto;
}
/* ------------- */
.screenshot{
  height: 50%;
  width: 100%;
  box-shadow: 0px 0px 20px 0px rgb(0 0 0 / 60%);
}
.screenshot img{
  height: 100%;
  /* max-width: 100%; */
  width: 100%;
  border-radius: 5px 5px 0 0;
  object-fit: cover;
  object-position: center top;

}
/* ------------- */
.content_wrap{
  height: 40%;
  width: 100%;
  padding: 5%;
  background-color: white;
  color: black;
  box-shadow: inset 0px 0px 7px 0px rgb(0 0 0 / 60%);
  border-radius: 0 0 5px 5px;

}
.content1{
  height: 40%;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
    .content1_left{
      height: 100%;
      width: 65%;
      text-align: left;
    }
        .content1_icon{
          height: 50%;
        }
            .content1_icon img{
              height: 100%;
              padding: 3%;
            }
        .content1_title{
          height: 25%;
          padding: 3%;
          font-weight: bold;
        }
        .content1_url{
          height: 25%;
          padding: 3%;
          overflow: hidden;
          text-overflow: ellipsis;
          width: 100%;
          white-space: nowrap;
          font-size: x-small;
        }
          .content1_url a{
            text-decoration: underline;
            color: cadetblue;
            cursor: pointer;
          }
    .content1_right{
      height: 100%;
      width: 35%;
    }
        .content1_right img{
          padding: 3%;
          width:auto;
          height:auto;
          max-width:100%;
          max-height:100%;
        }
.content2{
  height: 40%;
  padding: 1em 0.3em;
  font-size: small;
  text-align: start;
}
.content3{
  height: 20%;
  padding: 1em 0;
  display: flex;
  justify-content: space-evenly;
  text-decoration: underline;
  color: cadetblue;
  /* cursor: pointer; */
}
.content3 p{
  cursor: pointer;  
}
/* ------------- */
.close_area{
  height: 10%;
  padding-top: 1em;
}
  .close_area svg{
    cursor: pointer;
    transition: 0.5s;
  }
  .close_area svg:hover{
    transform: scale(1.2);
  }
/* ------------- */
</style>
