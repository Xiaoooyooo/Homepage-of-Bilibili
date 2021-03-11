<template>
  <div class="module-container">
    <div class="module-left">
      <module-tab>
        <div slot="tab_left">
          <i class="blbl-icon module-log log"></i>
          <a href="javascript:;" class="module-name">特别推荐</a>
        </div>
      </module-tab>
      <ul class="module-left-main">
        <li class="sp-recommendation-item" v-for="(i, index) in 5" :key="index">
          <a class="sp-recommendation-item-info" href="javascript:;">
            <div class="sp-re-cover" :style="'background-image:url('+rec.bg+')'">
              <a href="javascript:;" class="watch-later" title="稍后再看"></a>
            </div>
            <p class="sp-re-title">一些文字说明一些文字说明一些文字说明</p>
          </a>
          <div class="sp-re-profile">
            <a href="javascript:;">
              <div class="sp-re-pic">
                <img :src="rec.href" alt="" />
              </div>
              <span class="sp-re-user">xxxxx</span>
            </a>
            <span style="vertical-align: 7px">推荐</span>
          </div>
        </li>
      </ul>
    </div>
    <div class="module-right">
      <a class="sp-recommendation-pic" href="javascript:;">
        <img
          src="https://pic.netbian.com/uploads/allimg/201111/232308-16051081887e56.jpg"
          alt=""
        />
      </a>
    </div>
  </div>
</template>
<script>
import moduleTab from "../common/moduleTab";
export default {
  data() {
    return {
      rec: {
        href:
          "https://pic.netbian.com/uploads/allimg/201215/191055-16080306551b6e.jpg",
          bg: 'https://pic.netbian.com/uploads/allimg/201111/235645-16051102059342.jpg'
      },
    };
  },
  components: {
    moduleTab,
  },
};
</script>
<style scoped>
.log {
  background-position: -141px -780px;
}
.sp-recommendation-item {
  position: relative;
  width: 160px;
  height: 160px;
}
.sp-recommendation-item-info {
  text-decoration: none;
  color: #222;
  transition: all 0.3s ease;
  height: 100%;
  width: 100%;
}
.watch-later {
  display: none;
  position: absolute;
  right: 6px;
  bottom: 4px;
  height: 22px;
  width: 22px;
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABYAAAAWCAYAAADEtGw7AAABT0lEQVQ4je3VMYrCQBTG8b/DWASLNKJgJ1hY2sloZeF2gkeYW+wZvIVXsLBJY5UdtLJLk17EIghCwChukWRxFzSaaLdfMwm8/EgemTclgOl02gEmwAAoky8RsAA+tdbrUoJ+AVZO8G9CoCeJ39Sq1+sopbBtO5e23+8xxrDdbi1gIog/vxAKYNs2Sqn0diBIenoP9X2fIAgyccv66WZZZBXvdjtc18UYkwlfJxM+n8+/1pfBefMPPw4LEZcEQcBqteJ0Or0GrlartFotLpcLnucxm83YbDbFYSEE/X6f4XBIpVLhcDjgOA6u63I8HvPDaRqNBuPxmHa7DcS7cT6f36yXj8IAUkq63S7NZpPlcomUtx9/Ck5Tq9UYjUZ3a976u0UQz9OiCcMwvYwk8XHyYYxBKXU9+p5Grybg4m1Hk9Bar4Ee4JC0JWeixOhprdffE/1yRW/TLMYAAAAASUVORK5CYII=);
}
.sp-recommendation-item-info:hover {
  color: #00a1d6;
}
.sp-recommendation-item-info:hover .watch-later {
  display: block;
}
.sp-re-cover {
  position: relative;
  height: 100px;
  width: 160px;
  background-size: cover;
  /* background-repeat: no-repeat;
  background-position: center; */
  border-radius: 4px;
  overflow: hidden;
}

.sp-re-title {
  margin-top: 24px;
  height: 40px;
  line-height: 20px;
}
.sp-re-profile {
  position: absolute;
  bottom: 34px;
  left: 5px;
}
.sp-re-profile a {
  text-decoration: none;
  color: #222;
  transition: all 0.3s ease;
}
.sp-re-profile a:hover {
  color: #00a1d6;
}
.sp-re-profile > span {
  color: #aaa;
}
.sp-re-pic {
  display: inline-block;
  height: 45px;
  width: 45px;
  border-radius: 50%;
  border: 2px solid #fff;
  overflow: hidden;
}
.sp-re-pic img {
  height: 100%;
  width: 100%;
}
.sp-re-user {
  display: inline-block;
  padding-left: 5px;
  vertical-align: super;
  width: 68px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.sp-recommendation-pic {
  display: block;
  width: inherit;
  height: 150px;
  margin-top: 45px;
}
.sp-recommendation-pic img {
  width: 100%;
  height: 100%;
  border-radius: 4px;
}
</style>
