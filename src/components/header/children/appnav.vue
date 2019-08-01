<template>
    <div class="navbar-container">
        <div class="nav-mask"></div>
        <div class="navbar">
          <ul class="left-nav">
            <li @mouseleave="hide" class="items" v-for="item in leftList" :key="item.id">
              <a
                class="items-each"
                @mouseenter="show(item.id)"
                :title="item.name"
                href="javascript:;"
              >{{item.name}}</a>
              <transition name="nav">
                <!-- 悬停 下载APP 时出现内容 -->
                <download v-if="item.id==showIndex&&item.id==9" />
              </transition>
            </li>
          </ul>
          <ul class="right-nav">
            <li class="items" v-for="item in rightList" :key="item.id">
              <div class="profile" @mouseleave="hideInfoMenu" v-if="item.id==1" href="javascript:;">
                <div @mouseenter="showInfoMenu" class="profile-pic"></div>
                <transition name="profile">
                  <login-false v-if="showMenu" />
                </transition>
              </div>
              <a v-else class="items-each" href="javascript:;">{{item.name}}</a>
            </li>
          </ul>
          <div class="contribute">
            <a href="javascript:;">投稿</a>
          </div>
        </div>
      </div>
</template>
<script>
import download from "./header-download.vue";
import loginFalse from "./header-login-false.vue";

export default {
    data(){
        return{
            leftList: [
        {
          id: 1,
          name: "主站"
        },
        {
          id: 2,
          name: "音频"
        },
        {
          id: 3,
          name: "游戏中心"
        },
        {
          id: 4,
          name: "直播"
        },
        {
          id: 5,
          name: "会员购"
        },
        {
          id: 6,
          name: "漫画"
        },
        {
          id: 7,
          name: "BML"
        },
        {
          id: 8,
          name: "70年"
        },
        {
          id: 9,
          name: "下载APP"
        }
      ],
      rightList: [
        {
          id: 1,
          name: "",
          src: "https://static.hdslb.com/images/akari.jpg"
        },
        {
          id: 7,
          name: "历史"
        }
      ],
      showIndex: null,
      showMenu: false
        }
    },
    methods: {
    showInfoMenu() {
      this.showMenu = true;
    },
    hideInfoMenu() {
      this.showMenu = false;
    },
    show(i) {
      this.showIndex = i;
    },
    hide() {
      this.showIndex = null;
    }
  },
    components: {
    download,
    loginFalse
  }
}
</script>
<style scoped>
/* 动画相关 */
.nav-enter,
.nav-leave-to {
  opacity: 0;
  transform: translateY(20px);
}
.nav-enter-active,
.nav-leave-active {
  transition: all 0.5s ease;
}

.profile-enter,
.profile-leave-to {
  opacity: 0;
  transform: translateY(20px);
}
.profile-enter-active,
.profile-leave-active {
  transition: all 0.5s ease;
}
.navbar-container {
  position: relative;
  height: 42px;
  width: 100%;
  background: inherit;
}
.navbar-container::before {
  content: "";
  height: 100%;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background: inherit;
  filter: blur(5px);
}
.nav-mask {
  position: absolute;
  height: 100%;
  width: 100%;
  background: rgba(255, 255, 255, 0.4);
  box-shadow: rgba(255, 255, 255, 0.1) 0 0 3px 3px;
}
.navbar {
  position: relative;
  margin: 0 auto;
  height: 100%;
  width: 1160px;
  min-width: 980px;
  display: flex;
}
.left-nav {
  display: flex;
  height: 100%;
  width: 50%;
}
.right-nav {
  display: flex;
  justify-content: flex-end;
  height: 100%;
  width: 50%;
}
.items {
  position: relative;
  font-size: 12px;
  line-height: 42px;
}

.items-each {
  padding: 0 5px;
  box-sizing: border-box;
  color: #000;
  display: block;
  height: 100%;
  width: 100%;
  text-decoration: none;
}
.items-each:hover {
  background: rgba(255, 255, 255, 0.5);
}
.profile {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.profile-pic {
  cursor: pointer;
  margin: 5px;
  height: 32px;
  width: 32px;
  border-radius: 50%;
  background: url("https://static.hdslb.com/images/akari.jpg") no-repeat 0 0;
  background-size: cover;
  transition: all 0.5s ease;
}
.contribute {
  margin: 0 5px;
  height: 100%;
  width: 68px;
}
.contribute > a {
  display: block;
  height: 110%;
  width: 100%;
  text-align: center;
  line-height: 42px;
  text-decoration: none;
  background: #f45a8d;
  color: #fff;
  border-radius: 0 0 5px 5px;
}
.contribute > a:hover {
  background: #fb7299;
}
</style>
