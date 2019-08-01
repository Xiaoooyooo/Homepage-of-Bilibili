<template>
    <div class="nav-main-container">
      <ul class="nav-main">
        <li v-for="item in navLists" :key="item.name">
          <a href="javascript:;">
            <span
              :class="{'nav-main-num':1,'blbl-icon nav-pic home':item.name=='首页','blbl-icon nav-pic nav-zl':item.name=='专栏','blbl-icon nav-pic nav-live':item.name=='直播','blbl-icon nav-pic nav-gc':item.name=='广场','blbl-icon nav-pic nav-black':item.name=='小黑屋'}"
            >{{item.num}}</span>
            <span class="nav-main-i">{{item.name}}</span>
          </a>
        </li>
      </ul>
      <div class="gif">
        <a href="javascript:;">
          <img
            src="https://i0.hdslb.com/bfs/archive/53dbf75433cf6ccd568a3fac001c476ee20724c0.gif"
            alt
          />
        </a>
      </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            navLists: [
        {
          name: "首页",
          num: "",
          href: ""
        },
        {
          name: "动画",
          num: 999,
          href: ""
        },
        {
          name: "番剧",
          num: 999,
          href: ""
        },
        {
          name: "国创",
          num: 999,
          href: ""
        },
        {
          name: "音乐",
          num: 999,
          href: ""
        },
        {
          name: "舞蹈",
          num: 999,
          href: ""
        },
        {
          name: "游戏",
          num: 999,
          href: ""
        },
        {
          name: "科技",
          num: 999,
          href: ""
        },
        {
          name: "数码",
          num: 999,
          href: ""
        },
        {
          name: "生活",
          num: 999,
          href: ""
        },
        {
          name: "鬼畜",
          num: 999,
          href: ""
        },
        {
          name: "时尚",
          num: 999,
          href: ""
        },
        {
          name: "广告",
          num: 999,
          href: ""
        },
        {
          name: "娱乐",
          num: 999,
          href: ""
        },
        {
          name: "影视",
          num: 999,
          href: ""
        },
        {
          name: "放映厅",
          num: 999,
          href: ""
        },
        {
          name: "专栏",
          num: "",
          href: ""
        },
        {
          name: "直播",
          num: "",
          href: ""
        },
        {
          name: "广场",
          num: "",
          href: ""
        },
        {
          name: "小黑屋",
          num: "",
          href: ""
        }
      ],
        }
    }
}
</script>
<style scoped>
.nav-main-container {
  height: 60px;
  width: 1160px;
  min-width: 980px;
  margin: 0 auto;
  font-size: 12px;
  display: flex;
}
.nav-main-container a {
  text-decoration: none;
  display: flex;
  flex-direction: column;
}
.nav-main {
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.nav-main-num {
  margin:1px 0;
  text-align: center;
  padding:0 3px;
  color: #fff;
  background-color: #ffafc9;
  border-radius: 3px;
  transform: scale(0.85);
}
.nav-main-i {
  text-align: center;
  color: #222;
}
.nav-pic {
  margin:0 auto;
  box-sizing: border-box;
  width: 18px;
  height: 18px;
  background-color: transparent;
}

.home {
    background-position: -663px -1175px;
}
.nav-zl {
  background-position: -87px -1814px;
}
.nav-gc {
  background-position: -87px -2006px;
}
.nav-live {
  background-position: -87px -1878px;
}
.nav-black {
  background-position: -87px -1942px;
}
.gif {
  margin-left: 16px;
  padding: 10px 0;
}
.gif a{
    width: 69px;
  height: 40px;
  border-radius: 3px;
    overflow: hidden;
}
.gif img{
    width: 100%;
    height:100%;
}
</style>
