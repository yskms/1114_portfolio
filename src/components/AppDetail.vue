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
        "https://github.com/yskms/practice07-othello",],
      figmaArr:[
        "https://pitchdeck.hypermatic.com/slides/l9rx5yyj40410?token=VjR4biQlU2lIYmhIelo%3D",
        "",
        "",
        "",],
    }
  },
  methods:{
    useParentOpenAppDetail(n){
      this.$emit('openAppDetail',n);
    },
    pageTop() {
      document.getElementById("appDetail_cont_id").scrollTo({
        top: 0,
        behavior: 'smooth'
      });
      console.log('pagetop');
    },
  },
  watch:{
    detailNumber: {
        // immediate: true,
        handler: function () {
          console.log("aaa");
          this.pageTop();
        }
    },
  },
}
</script>

<template>
  <div class="appDetail_cont" id="appDetail_cont_id">
    <!-- 0 -->
    <div class="appDetail_main" v-show="detailNumber==0">
        <div class="title_cont">
          <div class="title_icon"><img src="../assets/hakase3.png"></div>
          <h1>国旗ハカセ</h1>
        </div>
        <a class="app_url" target="_blank" href="https://remarkable-salmiakki-887cba.netlify.app">https://remarkable-salmiakki-887cba.netlify.app</a>
        <div class="ss_cont">
          <div class="ss">
            <img src="../assets/hakase_ss1.png">
          </div>
          <div class="ss">
            <img src="../assets/hakase_ss2.png">
          </div>
          <div class="ss">
            <img src="../assets/hakase_ss3.png">
          </div>
          <div class="ss">
            <img src="../assets/hakase_ss4.png">
          </div>
          <div class="ss">
            <img src="../assets/hakase_qr.png">
          </div>
        </div>
        <h2>Character<span class="small">アプリの特徴</span></h2>
        <li>国旗クイズアプリ</li>
        <li>ユーザー登録、スコアのランキング登録が可能</li>
        <li>プレイ回数やスコアによってゲームモードが追加</li>
        
        <h2>Technology<span class="small">使用技術</span></h2>
        <li>Vue 2</li>
        <li>Vue Router</li>
        <li>firebase : ユーザー認証、データベース</li>
        <li>dayjs : 日時表示</li>
        <li>Vuetify : UI</li>

        <h2>Structure<span class="small">構成</span></h2>
        <li>Vue Routerでの画面遷移は5画面</li>
        <li>ユーザー認証画面とゲーム結果表示は、コンポーネントを全画面表示して実装</li>
        <div class="kousei" id="hakase_kousei"><img src="../assets/hakase_kousei2.jpg"></div>

        <h2>Challenges<span class="small">挑戦したこと</span></h2>
        <li>利用者を小学校低学年と想定し、操作の分かりやすさ、動きのあるデザインを意識した</li>
        <li>メソッド名やコメントで可読性を意識してコーディングした</li>
        <li>想定外の操作をされてもエラーが起きにくいように、Vue Routerと例外処理を細かく組み込んだ</li>

        <h2>Impressions<span class="small">感想</span></h2>
        <li>分かりやすいUIを作成する難しさを感じた</li>
        <li>制作中は読みやすいコードと思っていたが、説明に詳細さが足りない部分がある</li>
        <li>ルール設定に誤りがあったのか、firebase関連のエラーが発生している</li>

        <h2>Future<span class="small">今後の課題</span></h2>
        <li>デザインの修正と統一（Vuetifyの除去）</li>
        <li>ゲームモードの追加、修正（解答時に一時停止など）</li>
        <li>firebaseのバグ修正</li>
        <li>スマホアプリ化してGooglePlayStoreにリリースしたい</li>

        <h2>GitHub<span class="small">ソースコード</span></h2>
        <li><a class="github_url" target="_blank" href="https://github.com/yskms/1023_flag_app_v2">https://github.com/yskms/1023_flag_app_v2</a></li>
    </div>
    <!-- 0 -->
    <!-- 1 -->
    <div class="appDetail_main" v-show="detailNumber==1">
        <div class="title_cont">
          <div class="title_icon"><img src="../assets/rikare.svg"></div>
          <h1>リカレめし</h1>
        </div>
        <a class="app_url" target="_blank" href="https://deft-toffee-382a3f.netlify.app/">https://deft-toffee-382a3f.netlify.app/</a>
        <div class="ss_cont">
          <div class="ss">
            <img src="../assets/rikare_ss1.png">
          </div>
          <div class="ss">
            <img src="../assets/rikare_ss2.png">
          </div>
          <div class="ss">
            <img src="../assets/rikare_ss3.png">
          </div>
          <div class="ss">
            <img src="../assets/rikare_ss4.png">
          </div>
          <div class="ss">
            <img src="../assets/rikare_qr.png">
          </div>
        </div>
        <h2>Character<span class="small">アプリの特徴</span></h2>
        <li>オススメごはん屋さんを投稿できるアプリ</li>
        <li>写真や位置情報を登録できる</li>
        <li>創造社リカレントスクール周辺の表示に特化</li>
        
        <h2>Technology<span class="small">使用技術</span></h2>
        <li>Vue 2</li>
        <li>firebase : データベース、データストレージ</li>
        <li>leaflet : 地図表示</li>
        <li>Compressor.js : 画像サイズ圧縮</li>

        <h2>Structure<span class="small">構成</span></h2>
        <li>1画面のみ</li>
        <li>店舗詳細画面と投稿・修正画面は、コンポーネントをポップアップ表示して実装</li>
        <li>店舗詳細 >> 修正 >> 店舗詳細と画面遷移しても反映されるように、ライフサイクルフックを活用</li>
        <div class="kousei" id="rikare_kousei"><img src="../assets/rikare_kousei.jpg"></div>

        <h2>Challenges<span class="small">挑戦したこと</span></h2>
        <li>生徒が作ったアプリとして、継続して稼働させる事を目標にして制作</li>
        <li>シンプルさ、押せそうなところが押せる直感的操作を意識した</li>
        <li>開発の速さを意識した</li>

        <h2>Impressions<span class="small">感想</span></h2>
        <li>完成度不足、プレゼン不足もあり、採用されるには至らなかった</li>
        <li>デザインの発想力や引き出しが足りていない。細部の雑さが目立つ</li>
        <li>直感的操作はそれなりに実現できたと思うが、細部の表示等がツメが甘い</li>
        <li>機能をしっかり厳選して、2週間でほぼ完成できたのは良い点</li>

        <h2>Future<span class="small">今後の課題</span></h2>
        <li>細部までしっかりデザインする事で、総合的な完成度を高める事を意識する</li>
        <li>ほぼ同じ構成で実現できるアプリの案が複数あるので、今回の経験を活かしたい</li>

        <h2>GitHub<span class="small">ソースコード</span></h2>
        <li><a class="github_url" target="_blank" href="https://github.com/yskms/1117_rikameshi">https://github.com/yskms/1117_rikameshi</a></li>
    </div>
    <!-- 1 -->
    <!-- 2 -->
    <div class="appDetail_main" v-show="detailNumber==2">
        <div class="title_cont">
          <div class="title_icon"><img src="../assets/utc_white.svg"></div>
          <h1>UTC NOW</h1>
        </div>
        <a class="app_url" target="_blank" href="https://chic-lebkuchen-daab8b.netlify.app/">https://chic-lebkuchen-daab8b.netlify.app/</a>
        <div class="ss_cont">
          <div class="ss">
            <img src="../assets/utc_ss1.png">
          </div>
          <div class="ss">
            <img src="../assets/utc_ss2.png">
          </div>
          <div class="ss">
            <img src="../assets/utc_ss3.png">
          </div>
          <div class="ss">
            <img src="../assets/utc_qr.png">
          </div>
        </div>
        <h2>Character<span class="small">アプリの特徴</span></h2>
        <li>UTC（協定世界時）を表示させるだけのシンプルアプリ</li>
        <li>タップ操作のみで操作可能</li>
        
        <h2>Technology<span class="small">使用技術</span></h2>
        <li>Vue 2</li>
        <li>vuejs-datepicker : カレンダー</li>

        <h2>Structure<span class="small">構成</span></h2>
        <li>1画面のみ</li>
        <div class="kousei"><img src="../assets/utc_kousei.jpg"></div>

        <h2>Challenges<span class="small">挑戦したこと</span></h2>
        <li>日付、時間の取り扱いに想像以上に苦労した</li>
        <li>モノトーンの極端にシンプルなデザインを採用</li>
        <li>開発の速さを意識</li>

        <h2>Impressions<span class="small">感想</span></h2>
        <li>Dateクラスの取り扱いに際し、基本的なJavaScriptの理解不足を感じた</li>
        <li>細部のデザインに詰めの甘さが出てしまっている</li>
        <li>3日で完成を目指したが、見通しが甘く5日掛かってしまった</li>

        <h2>Future<span class="small">今後の課題</span></h2>
        <li>オブジェクト指向などまだまだ理解不足な部分があるので、適宜参考書の読み返しなどで理解を深めていきたい</li>
        <li>デザインについては当初気付けなかった部分が見えるようになってきているので、もっと経験を積んでいきたい</li>

        <h2>GitHub<span class="small">ソースコード</span></h2>
        <li><a class="github_url" target="_blank" href="https://github.com/yskms/1205_utc_now_v3">https://github.com/yskms/1205_utc_now_v3</a></li>
    </div>
    <!-- 2 -->
    <!-- 3 -->
    <div class="appDetail_main" v-show="detailNumber==3">
        <div class="title_cont">
          <div class="title_icon"><img src="../assets/othello.svg"></div>
          <h1>VanillaJS-オセロ</h1>
        </div>
        <a class="app_url" target="_blank" href="https://voluble-macaron-a9260e.netlify.app/">https://voluble-macaron-a9260e.netlify.app/</a>
        <div class="ss_cont">
          <div class="ss">
            <img src="../assets/othello_ss1.png">
          </div>
          <div class="ss">
            <img src="../assets/othello_ss2.png">
          </div>
          <div class="ss">
            <img src="../assets/othello_ss3.png">
          </div>
          <div class="ss">
            <img src="../assets/othello_qr.png">
          </div>
        </div>
        <h2>Character<span class="small">アプリの特徴</span></h2>
        <li>オセロゲームのアプリ</li>
        <li>置けるマスが色付け表示される</li>
        <li>プレイ途中でも集計可能</li>
        
        <h2>Technology<span class="small">使用技術</span></h2>
        <li>JavaScript</li>

        <h2>Structure<span class="small">構成</span></h2>
        <li>1画面</li>
        <li>index.html</li>
        <li>main.css</li>
        <li>main.js</li>
        <!-- <div class="kousei"><img src="../assets/hakase_kousei2.jpg"></div> -->

        <h2>Challenges<span class="small">挑戦したこと</span></h2>
        <li>勉強初期段階で分からない事だらけだったが、ひたすらデバッグや理詰めで製作した</li>

        <h2>Impressions<span class="small">感想</span></h2>
        <li>配列で処理できるところを繰り返しで記述していたり、至らぬ点も多いが、デバッグやエラー処理は楽しみながら取り組めていた</li>
        <li>プログラミング楽しい！と思えたので良い経験だった</li>

        <!-- <h2>Future<span class="small">今後の課題</span></h2> -->

        <h2>GitHub<span class="small">ソースコード</span></h2>
        <li><a class="github_url" target="_blank" href="https://github.com/yskms/practice07-othello">https://github.com/yskms/practice07-othello</a></li>
    </div>
    <!-- 3 -->
    <!-- 4 -->
    <div class="appDetail_main" v-show="detailNumber==4">
        <div class="title_cont">
          <div class="title_icon"><img src="../assets/favicon.svg"></div>
          <h1>portforio</h1>
        </div>
        <a class="app_url" href="https://merry-medovik-f234a3.netlify.app/">https://merry-medovik-f234a3.netlify.app/</a>
        <div class="ss_cont">
          <div class="ss">
            <img src="../assets/portforio_ss1.png">
          </div>
          <div class="ss">
            <img src="../assets/portforio_ss2.png">
          </div>
          <div class="ss">
            <img src="../assets/portforio_ss3.png">
          </div>
          <div class="ss">
            <img src="../assets/portforio_qr.png">
          </div>
        </div>
        <h2>Character<span class="small">アプリの特徴</span></h2>
        <li>このポートフォリオ</li>
        <li>レスポンシブ対応</li>
        
        <h2>Technology<span class="small">使用技術</span></h2>
        <li>Vue 2</li>

        <h2>Structure<span class="small">構成</span></h2>
        <li>1画面</li>
        <li>アプリの詳細部分はコンポーネント化して表示</li>
        <div class="kousei"><img src="../assets/portforio_kousei.jpg"></div>

        <h2>Challenges<span class="small">挑戦したこと</span></h2>
        <li>ドキュメントを読んでもらえるようなデザインを目指した</li>
        <li>コンポーネント化することでメンテナンス性を高めた</li>
        <li>デザインの基本（コントラスト、反復、整列、近接）を意識した</li>

        <h2>Impressions<span class="small">感想</span></h2>
        <li>細部や基本を押さえることで、以前よりもデザインが改善したように思う</li>

        <h2>Future<span class="small">今後の課題</span></h2>
        <li>もう少し細部まで丁寧にUIを作り込んで、完成度を高めたい</li>

        <h2>GitHub<span class="small">ソースコード</span></h2>
        <li><a class="github_url" target="_blank" href="https://github.com/yskms/1114_portfolio">https://github.com/yskms/1114_portfolio</a></li>
    </div>
    <!-- 4 -->
    <!-- 99 スマホサイズ時の、menu押下時に表示する -->
    <div class="appDetail_main" v-show="detailNumber==99">
        <div class="sidebar_cont">
            <div class="sidebar">
              <div class="nav">
                <p class="whiteText">APPS</p>
                <!-- <p>GitHub</p> -->
                <!-- <p>SNS</p> -->
              </div>
              <div class="nav_list" >
                <p  class="nav_list_ttl" @click="useParentOpenAppDetail(0)" :class="{whiteText:(detailNumber==0)}">国旗ハカセ</p>
                <p  class="nav_list_ttl" @click="useParentOpenAppDetail(1)" :class="{whiteText:(detailNumber==1)}">リカレめし</p>
                <p  class="nav_list_ttl" @click="useParentOpenAppDetail(2)" :class="{whiteText:(detailNumber==2)}">UTC NOW</p>
                <p  class="nav_list_ttl" @click="useParentOpenAppDetail(3)" :class="{whiteText:(detailNumber==3)}">VanillaJS-オセロ</p>
                <p  class="nav_list_ttl" @click="useParentOpenAppDetail(4)" :class="{whiteText:(detailNumber==4)}">portforio</p>
              </div>
            </div>
          </div>
    </div>
    <!-- 99 -->
  </div><!-- appDetail_main -->
</template>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.appDetail_cont{
  background-color: rgb(0, 0, 0);
  color: aliceblue;
  height: 100%;
  width: 100%;
  border-radius: 1.5em;
  font-family: 'Noto Sans JP', sans-serif;
  overflow: auto;
}
    .appDetail_main{
      height: 100%;
      width: 80%;
      margin: 0 auto;
      background-color: rgb(0, 0, 0);
      text-align: left;
      padding-top: 0.5em;

      animation-name:clickAwake;
      animation-duration:3.5s;
      animation-fill-mode: forwards;
      opacity:0;
    }
    /* 1番下に余白を追加 */
    .appDetail_main::after {
      display: block;
      width: 1px;
      height: 8em;
      content: '';
    }
    /* じんわりと表示するアニメ */
    @keyframes clickAwake{
      0% {opacity: 0;  }
      /* 5% {opacity: 0;transform: translateX(0);} */
      45% {opacity: 1;transform: translateX(0);}
      100% {opacity: 1;transform: translateX(0);}
    }

/* ------メニュー表示用------- */
        .sidebar{
          width: 100%;
          height: 100%;
          background-color: rgb(0, 0, 0);
          border-radius: 1.5em;
          padding: 10%;
        }
            .nav{
              padding-top: 3em;
              display: flex;
              gap: 1em;
              justify-content: center;
              /* background-color: rgb(70, 151, 90); */
            }
                .nav p{
                  transition: 0.5s;
                  border-bottom: 1px gray solid;
                }
                /* .nav p:hover{
                  color: white;
                  border-bottom: 1px white solid;
                } */
                .whiteText{
                  color: white;
                  border-bottom: 1px white solid ;
                }
            .nav_list{
              background-color: rgb(0, 0, 0);
              /* padding: 1em 1em 1em 1em; */
              text-align: center;
              display: flex;
              flex-direction: column;
            }
                .nav_list_ttl{
                  display: inline;
                  padding-top: 1em;
                  border-bottom: 1px black solid;
                  transition: 0.5s;
                }
                .nav_list_ttl:hover{
                  color: white;
                  border-bottom: 1px gray solid;
                  cursor: pointer;
                }
/* ------フォント------- */
p{
  color: gray;
}
.app_url{
  color: gray;
  text-decoration: none;
  transition: 0.5s;
}
.app_url:hover{
  color: white;
}
.github_url{
  color: white;
  text-decoration: none;
}
h1{
  padding-left: 1rem;
  font-weight: 700;
}
h2{
  padding: 0.5rem;
  font-weight: 400;
  margin-top: 1rem;
}
/* 見出しのかすれていく下線 */
h2:after {
  content: "";
  display: block;
  height: 1px;
  background: -webkit-linear-gradient(to right, rgb(255, 255, 255), transparent);
  background: linear-gradient(to right, rgb(255, 255, 255), transparent);
}
/* 見出しの小さい文字 */
.small{
  font-size: 0.5em;
  padding-left: 1em;
}
li{
  font-weight: 200;
  /* list-style: none; */
  padding-left: 2em;
}
/* アプリのタイトル部分 */
.title_cont{
  height: 3rem;
  display: flex;
  margin-top: 1rem;
}
.title_icon{
  height: 100%;
}
.title_icon img{
  height: 90%;
}

/* スクリーンショット */
.ss_cont{
  height: 20rem;
  display: flex;
  gap: 1em;
  padding-left: 2rem;
  padding-top: 2rem;
  padding-bottom: 1rem;
  overflow: auto;
  width: 105%;
}
.ss_cont:after {
  content: "";
  display: block;
  height: 100%;
  background: -webkit-linear-gradient(to right, rgb(255, 255, 255), transparent);
  background: linear-gradient(to right, rgb(255, 255, 255), transparent);
}
.ss{
  height: 100%;
}
.ss img{
  height: 100%;
}

/* 構成の画像 */
.kousei{
  padding-top: 1rem;
  padding-left: 2rem;
  height: 10rem;
  overflow: auto;
  width: 105%;
}
.kousei img{
  height: 96%;
}
#hakase_kousei{
  height: 20rem;
}
#rikare_kousei{
  height: 15rem;
}
</style>
