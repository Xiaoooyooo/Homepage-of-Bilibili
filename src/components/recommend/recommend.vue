<template>
  <div class="recommend">
    <div @mouseleave="continueSlide" @mouseenter="stopSlide" class="recommend-slideshow">
      <ul class="slideshow-container" :style="'left:'+slideLeft+'%'">
        <li v-for="item in slideshows" :key="item.name">
          <a class="slideshow-item" href="javascript:;">
            <!-- <img class='imgs' :src="" :alt=""> -->
            <div class="imgs" :style="'background:#'+item.name"></div>
          </a>
        </li>
      </ul>
      <a href="javascript:;"></a>
    </div>
    <div class="recommend-vedio">
      <a class="vedio-item" v-for="video in videos" :key="video.title" href="javascript:;">
        <span class="vedio-info-mask">
          <span class="vedio-info">
            <p class="title">【一些文本......一些文本......一些文本......一些文本......】</p>
            <p class="a-p">up主：Xxx</p>
            <p class="a-p">播放：xx.xx</p>
          </span>
        </span>
      </a>
    </div>
  </div>
</template>
<script>
import { setInterval, clearInterval } from "timers";
export default {
  data() {
    return {
      videos: [
        {
          title: "one"
        },
        {
          title: "two"
        },
        {
          title: "three"
        },
        {
          title: "four"
        },
        {
          title: "five"
        },
        {
          title: "six"
        },
        {
          title: "seven"
        },
        {
          title: "eight"
        }
      ],
      slideshows: [
        {
          name: "bb1542"
        },
        {
          name: "eb5f5d"
        },
        {
          name: "fabc74"
        },
        {
          name: "239f95"
        },
        {
          name: "216583"
        }
      ],
      slideLeft: 0,
      timer: null
    };
  },
  methods: {
    stopSlide() {
      if (this.timer) clearInterval(this.timer);
    },
    continueSlide() {
      this.timer = setInterval(() => {
        this.slideLeft -= 100;
        if (this.slideLeft == -500) this.slideLeft = 0;
      }, 1000);
    }
  },
  mounted() {
    this.timer = setInterval(() => {
      this.slideLeft -= 100;
      if (this.slideLeft == -500) this.slideLeft = 0;
    }, 1000);
  }
};
</script>
<style scoped>
/* 动画相关 */
.recommend {
  width: 1160px;
  min-width: 980px;
  margin: 0 auto 40px;
  display: flex;
}
.recommend-slideshow {
  flex-shrink: 0;
  height: 220px;
  width: 440px;
  border-radius: 5px;
  background: lightcoral;
  overflow: hidden;
}
.slideshow-container {
  position: relative;
  display: flex;
  transition: all 0.5s ease;
}
.slideshow-item {
  /* display: block; */
  /* height: 220px;
  width: 440px; */
}
.imgs {
  display: inline-block;
  height: 220px;
  width: 440px;
}
.recommend-vedio {
  width: 720px;
  height: 220px;
  padding-left: 20px;
  display: flex;
  justify-content: space-between;
  align-content: space-between;
  flex-wrap: wrap;
}
.vedio-item {
  position: relative;
  width: 160px;
  height: 100px;
  background: url("https://s1.hdslb.com/bfs/static/jinkela/home/asserts/img_loading.png")
    no-repeat center;
  border-radius: 4px;
  overflow: hidden;
}
.vedio-info-mask {
  position: absolute;
  bottom: -10px;
  height: 40px;
  width: 100%;
  font-size: 12px;
  box-sizing: border-box;
  padding: 10px;
  color: #fff;
  background: linear-gradient(transparent,rgba(0,0,0,.1) 20%,rgba(0,0,0,.2) 35%,rgba(0,0,0,.6) 65%,rgba(0,0,0,.9));
}
.title{
	height:40px;
  line-height: 20px;
	overflow: hidden;
}
.a-p{
	opacity: 0;
	color:#99a2aa;
	transition: all 0.5s ease;
}

.vedio-item:hover .vedio-info-mask{
	bottom: 0;
	background: rgba(0,0,0,0.6);
	height:100%;
}
.vedio-item:hover .a-p{
	opacity: 1;
}
</style>
