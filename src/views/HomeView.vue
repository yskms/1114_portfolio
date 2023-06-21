<script>
import AppDetail from '@/components/AppDetail.vue'

export default {
  name: 'HomeView',
  components: { AppDetail },
  data(){
    return{
      navList:1, //現在未使用
      detailNumber:0,
        // 0:国旗ハカセ
        // 1:リカレめし
        // 2:UTC NOW
        // 3:VanillaJS-オセロ
        // 4:portforio
        // 99:menu
    }
  },
  methods:{
    openAppDetail(n){
      this.detailNumber=n
    },
    // 現状、APPのみなので未使用
    navSwitch(e){
      if(e==1){
        this.navList=1
      }else if(e==2){
        this.navList=2
      }
    },
  },
}
</script>

<template>
  <div class="bg">
    <!-- アクセス時アニメーション ------------------>
    <div class="intro">masashi yasaka</div>
    <!------------------------------------------>
    <div class="cont">
      <header class="header_cont">
        <div class="header">
          <div class="appicon" @click="openAppDetail(0)" :class="{appicon_selected:(detailNumber==0)}" ><img src="../assets/hakase3.png"></div>
          <div class="appicon" @click="openAppDetail(1)" :class="{appicon_selected:(detailNumber==1)}" ><img src="../assets/rikare.svg"></div>
          <div class="appicon" @click="openAppDetail(2)" :class="{appicon_selected:(detailNumber==2)}" ><img src="../assets/utc.svg"></div>
          <div class="appicon" @click="openAppDetail(3)" :class="{appicon_selected:(detailNumber==3)}" ><img src="../assets/othello.svg"></div>
          <div class="appicon" @click="openAppDetail(4)" :class="{appicon_selected:(detailNumber==4)}" ><img src="../assets/favicon.svg"></div>
          <div class="myname_cont">
            <div class="myname">masashi yasaka</div>
          </div>
          <div class="menu_cont">
            <div class="menu" @click="openAppDetail(99)" :class="{menu_cont_selected:(detailNumber==99)}" >menu</div>
          </div>
        </div>
      </header><!-- header -->
      <div class="main">
        <div class="sidebar_cont">
          <div class="sidebar">
            <div class="nav">
              <p class="whiteText">APPS</p>
              <!-- <p>GitHub</p> -->
              <!-- <p>SNS</p> -->
            </div>
            <div class="nav_list" >
              <p  class="nav_list_ttl" @click="openAppDetail(0)" :class="{whiteText:(detailNumber==0)}">国旗ハカセ</p>
              <p  class="nav_list_ttl" @click="openAppDetail(1)" :class="{whiteText:(detailNumber==1)}">リカレめし</p>
              <p  class="nav_list_ttl" @click="openAppDetail(2)" :class="{whiteText:(detailNumber==2)}">UTC NOW</p>
              <p  class="nav_list_ttl" @click="openAppDetail(3)" :class="{whiteText:(detailNumber==3)}">VanillaJS-オセロ</p>
              <p  class="nav_list_ttl" @click="openAppDetail(4)" :class="{whiteText:(detailNumber==4)}">portforio</p>
            </div>
          </div>
        </div>
        <div class="article">
          <AppDetail :detailNumber="detailNumber"
          @openAppDetail="openAppDetail"/>
        </div>
      </div><!-- main -->
    </div><!-- cont -->
    
  </div><!-- bg -->
</template>

<style scoped>
/* ================================================== */
/* デスクトップ用のCSS */
/* ================================================== */
p{
  color: gray;
}
.bg{
  background-color: rgb(255, 255, 255);
  width: 100vw;
  height: 100vh;
  font-family: 'Noto Sans JP', sans-serif;
  font-weight: 200;

}
.cont{
  height: 100vh;
  background-color: rgb(56, 54, 54);
}
  .header_cont{
    width: 100%;
    height: 10%;
    min-height: 90px;
    background-color: rgb(234 234 234);
    text-align: left;
    padding: 1%;
  }
      .header{
        height: 100%;
        margin: 0 auto;
        padding: 0.5em 0;
        background-color: rgb(255, 255, 255);
        border-radius: 1.5em;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        gap: 1.5em;
      }
          .appicon{
            height: 90%;
            /* min-width: 45px; */
            transition: 0.5s;
          }
          .appicon:hover{
            transform: scale(1.2);
            cursor: pointer;
          }
          .appicon_selected{
            transform: scale(1.2);
          }
          .appicon img{
            height: 100%;
            width: 100%;
            object-fit: contain;
          }
          .myname_cont{
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            /* background-color: rgb(222, 222, 244); */
            display: flex;
            align-items: center;
            font-weight: 200;
            font-size: 1.8em;
            padding-left: 2.5%;
          }
          /* .myname_cont:hover{transform: scale(2);} */
          .menu_cont{
            display: none;
          }
  .main{
    width: 100%;
    height: 90%;
    background-color: rgb(234 234 234);
    display: flex;
  }
      .sidebar_cont{
        width: 25%;
        height: 100%;
        background-color: rgb(234 234 234);
        padding: 1%;
      }
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
              /* background-color: rgb(70, 151, 90); */
            }
                .nav p{
                  transition: 0.5s;
                  border-bottom: 1px gray solid;
                }
                /*  */
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
              text-align: left;
              display: flex;
              flex-direction: column;
            }
                .nav_list_ttl{
                  padding-top: 1em;
                  border-bottom: 1px black solid;
                  transition: 0.5s;
                }
                .nav_list_ttl:hover{
                  color: white;
                  border-bottom: 1px gray solid;
                  cursor: pointer;
                }
      .article{
        width: 75%;
        height: 100%;
        background-color: rgb(234 234 234);
        padding: 1%;
        margin: 0 auto;
      }
/* ================================================== */
/* スマホ、タブレット用のCSS */
/* ================================================== */
@media screen and (max-width: 830px) {
p{
  color: gray;
}
.bg{
  background-color: rgb(255, 255, 255);
  width: 100vw;
  height: 100vh;
  font-family: 'Noto Sans JP', sans-serif;
  font-weight: 200;
  min-width: 350px;

}
.cont{
  height: 100vh;
  background-color: rgb(56, 54, 54);
}
  .header_cont{
    width: 100%;
    height: 10%;
    min-height: 90px;
    background-color: rgb(234 234 234);
    text-align: left;
    padding: 1%;
  }
      .header{
        height: 100%;
        margin: 0 auto;
        padding: 0.5em 1em;
        background-color: rgb(255, 255, 255);
        border-radius: 1.5em;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        gap: 1.5em;
      }
          .appicon{
            height: 90%;
            /* min-width: 45px; */
            transition: 0.5s;
          }
          .appicon:hover{
            transform: scale(1.2);
            cursor: pointer;
          }
          .appicon_selected{
            transform: scale(1.2);
          }
          .appicon img{
            height: 100%;
            width: 100%;
            object-fit: contain;
          }
          .myname_cont{
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            /* background-color: rgb(222, 222, 244); */
            display: flex;
            align-items: center;
            font-weight: 200;
            font-size: 1.8em;
            display: none;
          }
          /* .myname_cont:hover{transform: scale(2);} */
          .menu_cont{
            display: block;
            transition: 0.5s;
            color: gray;
          }
          .menu_cont:hover{
            color: black;
            cursor: pointer;
          }
          .menu_cont_selected{
            color: black;
          }
  .main{
    width: 100%;
    height: 90%;
    background-color: rgb(234 234 234);
    display: flex;
  }
      .sidebar_cont{
        width: 25%;
        height: 100%;
        background-color: rgb(234 234 234);
        padding: 1%;
        display: none;
      }
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
                  border-bottom: 1px gray solid ;
                }
            .nav_list{
              background-color: rgb(0, 0, 0);
              /* padding: 1em 1em 1em 1em; */
              text-align: left;
              display: flex;
              flex-direction: column;
            }
                .nav_list_ttl{
                  padding-top: 1em;
                  border-bottom: 1px black solid;
                  transition: 0.5s;
                }
                .nav_list_ttl:hover{
                  color: white;
                  border-bottom: 1px gray solid;
                  cursor: pointer;
                }
      .article{
        width: 100%;
        height: 100%;
        background-color: rgb(234 234 234);
        padding: 1%;
        margin: 0 auto;
      }
}

/* アクセス時アニメーション 共通--------------------------------------------*/
.intro{
  position: absolute;
  top: 45%;
  width: 100%;
  font-weight: 200;
  font-size: 2em;
  animation-name:introMyname;
  animation-duration:3s;
  animation-fill-mode: forwards;
  opacity:0;
  /* text-shadow: 2px 3px 3px rgba(0, 0, 0, 0.2); */
}
@keyframes introMyname{
  0% {opacity: 0;}
  20% {opacity: 1;transform: translateX(0);}
  60% {opacity: 0.9;transform: translateX(0);}
  80% {opacity: 0;transform: translateX(0);}
}
.cont{
  animation-name:introAwake;
  animation-duration:8s;
  animation-fill-mode: forwards;
  opacity:0;
}
@keyframes introAwake{
  0% {opacity: 0;  }
  35% {opacity: 0;transform: translateX(0);}
  55% {opacity: 1;transform: translateX(0);}
  100% {opacity: 1;transform: translateX(0);}
}
/* アクセス時アニメーション ここまで--------------------------------------------*/
</style>