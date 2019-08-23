<template>
  <aside class="aside-container" :style="'top:'+scrollY+'px'">
    <div class="side-bar-content">
      <a href="javascript:;" class="aside-item" v-for="item in sideBarList" :key="item">{{item}}</a>
      <a href="javascript:;" class="side-bar-controler">
        <i class="blbl-icon side-bar-icon customize"></i>
      </a>
      <a href="javascript:;" class="side-bar-controler">
        <i class="blbl-icon side-bar-icon go-top"></i>
      </a>
    </div>
    <div class="side-bar-download">
      <a href="javascript:;">
        <div
          class="side-bar-download-animation"
          @mouseover="downloadAnimation"
          @mouseout="clearAnimation"
          :style="'background-position-x:'+bg_x+'px'"
        ></div>
        <transition name="side-bar-downlaod">
          <div v-show="showSideTips" class="side-bar-download-tips"></div>
        </transition>
      </a>
    </div>
  </aside>
</template>
<script>
import { setInterval, clearInterval } from "timers";
export default {
  data() {
    return {
      showSideTips: false,
      ani_timer: null,
      bg_dx: 80,
      bg_x: 0,
      scrollY: 230,
      sideBarList: [
        "直播",
        "动画",
        "番剧",
        "国创",
        "漫画",
        "音乐",
        "舞蹈",
        "游戏",
        "科技",
        "数码",
        "生活",
        "鬼畜",
        "时尚",
        "广告",
        "娱乐",
        "专栏",
        "电影",
        "TV剧",
        "影视",
        "纪录片"
      ]
    };
  },
  methods: {
    downloadAnimation() {
      this.showSideTips = true;
      if (this.ani_timer) clearInterval(this.ani_timer);
      this.ani_timer = setInterval(() => {
        if (this.bg_x <= -1200 && this.bg_dx > 0) this.bg_dx = -1 * this.bg_dx;
        if (this.bg_x >= -720 && this.bg_dx < 0) this.bg_dx = -1 * this.bg_dx;
        this.bg_x -= this.bg_dx;
      }, 100);
    },
    clearAnimation() {
      this.showSideTips = false;
      if (this.ani_timer) clearInterval(this.ani_timer);
      this.ani_timer = setInterval(() => {
        this.bg_x += 80;
        if (this.bg_x == 0) {
          clearInterval(this.ani_timer);
          this.bg_dx = 80;
        }
      }, 100);
    }
  },
  mounted() {
    var H = window.innerHeight;
    var x = (H - 634) / 2;
    var offsetY = x < 0 ? 0 : x;
    window.onresize = () => {
      H = window.innerHeight;
			x = (H - 634) / 2;
			offsetY = x < 0 ? 0 : x;
    };
    window.onscroll = () => {
      this.scrollY = window.scrollY >= 230 ? offsetY : 230;
    };
  }
};
</script>
<style scoped>
/* 动画 */
.side-bar-downlaod-enter,
.side-bar-downlaod-leave-to {
  opacity: 0;
}
.side-bar-downlaod-enter-active,
.side-bar-downlaod-leave-active {
  transition: all 0.5s ease;
}

.aside-container {
  position: fixed;
  top: 230px;
  transform: translateX(120%);
  width: auto;
  background-color: #f6f9fa;
  background-color: #fff;
  transition: all 0.3s ease;
}
.side-bar-content {
  padding-top: 6px;
  border: 1px solid #e5e9ef;
  border-radius: 4px;
  overflow: hidden;
}
.aside-item {
  display: block;
  text-decoration: none;
  color: #222;
  width: 48px;
  height: 24px;
  line-height: 24px;
  text-align: center;
  transition: all 0.3s ease;
}
.aside-item-checked {
  background-color: #00a1d6;
  color: #fff;
}
.side-bar-controler {
  display: block;
  height: 16px;
  padding: 8px 0;
  border-top: 1px solid #e5e9ef;
  transition: all 0.3s ease;
}
.aside-item:hover,
.side-bar-controler:hover {
  background-color: #00a1d6;
  color: #fff;
}
.side-bar-icon {
  display: block;
  height: 18px;
  width: 18px;
  margin: 0 auto;
  transform: scale(0.7);
}
.customize {
  background-position: -663px -151px;
}
.go-top {
  background-position: -663px -89px;
}
.side-bar-controler:hover .customize {
  background-position: -727px -151px;
}
.side-bar-controler:hover .go-top {
  background-position: -727px -89px;
}
.side-bar-download {
  position: relative;
  width: 50px;
}
.side-bar-download-animation {
  position: relative;
  left: 15px;
  width: 80px;
  height: 80px;
  background: url(https://s1.hdslb.com/bfs/static/jinkela/home/asserts/app-download.png)
    no-repeat;
}
.side-bar-download-tips {
  position: absolute;
  left: -110px;
  top: -20px;
  width: 106px;
  height: 44px;
  background-image: url(https://s1.hdslb.com/bfs/static/jinkela/home/asserts/app-download-tips.png);
}
</style>
