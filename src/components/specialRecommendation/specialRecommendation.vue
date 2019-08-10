<template>
  <div class="module-container">
    <div class="module-left">
      <module-tab>
        <div slot="tab_left">
          <i class="blbl-icon module-log log"></i>
          <a href="javascript:;" class="module-name">特别推荐</a>
        </div>
      </module-tab>
      <ul class='module-left-main'>
        <li class='sp-recommendation-item' v-for='(i,index) in 5' :key='index'>
          <a class='sp-recommendation-item-info' href="javascript:;">
            <div class='sp-re-cover'>
              <a href='javascript:;' class='watch-later' title='稍后再看'></a>
            </div>
            <p class='sp-re-title'>一些文字说明一些文字说明一些文字说明</p>
          </a>
          <div class='sp-re-profile'>
            <a href="javascript:;">
              <div class='sp-re-pic'>
                <img src="http://gss0.baidu.com/-fo3dSag_xI4khGko9WTAnF6hhy/zhidao/pic/item/32fa828ba61ea8d3bb01210a9b0a304e251f5898.jpg" alt="">
              </div>
              <span class='sp-re-user'>xxxxx</span>
            </a>
            <span style='vertical-align: 7px'>推荐</span>
          </div>
        </li>
      </ul>
    </div>
    <div class="module-right">
      <a class='sp-recommendation-pic' href="javascript:;">
        <img src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1565079768402&di=e3d2c852fca9c7984409fee8cf556152&imgtype=0&src=http%3A%2F%2Fimg3.duitang.com%2Fuploads%2Fitem%2F201407%2F31%2F20140731151410_a4FnZ.jpeg" alt="">
      </a>
    </div>
  </div>
</template>
<script>
import moduleTab from "../common/moduleTab";
export default {
  components: {
    moduleTab
  }
};
</script>
<style scoped>
.log{
    background-position: -141px -780px;
}
.sp-recommendation-item{
  position: relative;
  width: 160px;
  height: 160px;
}
.sp-recommendation-item-info{
  text-decoration: none;
  color: #222;
  transition: all 0.3s ease;
  height: 100%;
  width: 100%;
}
.watch-later{
  display: none;
  position: absolute;
  right: 6px;
  bottom: 4px;
  height: 22px;
  width: 22px;
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABYAAAAWCAYAAADEtGw7AAABT0lEQVQ4je3VMYrCQBTG8b/DWASLNKJgJ1hY2sloZeF2gkeYW+wZvIVXsLBJY5UdtLJLk17EIghCwChukWRxFzSaaLdfMwm8/EgemTclgOl02gEmwAAoky8RsAA+tdbrUoJ+AVZO8G9CoCeJ39Sq1+sopbBtO5e23+8xxrDdbi1gIog/vxAKYNs2Sqn0diBIenoP9X2fIAgyccv66WZZZBXvdjtc18UYkwlfJxM+n8+/1pfBefMPPw4LEZcEQcBqteJ0Or0GrlartFotLpcLnucxm83YbDbFYSEE/X6f4XBIpVLhcDjgOA6u63I8HvPDaRqNBuPxmHa7DcS7cT6f36yXj8IAUkq63S7NZpPlcomUtx9/Ck5Tq9UYjUZ3a976u0UQz9OiCcMwvYwk8XHyYYxBKXU9+p5Grybg4m1Hk9Bar4Ee4JC0JWeixOhprdffE/1yRW/TLMYAAAAASUVORK5CYII=);
}
.sp-recommendation-item-info:hover{
  color: #00a1d6;
}
.sp-recommendation-item-info:hover .watch-later{
  display: block;
}
.sp-re-cover {
  position: relative;
  height: 100px;
  width: 160px;
  background: url(https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1565080091606&di=84c0a41e8783978062fb79b671cabfba&imgtype=0&src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farchive%2Fbbe5dfc39f4cbdeccb027a834d6e0b921302545b.jpg) no-repeat center;
  background-image: url(https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1565080091606&di=84c0a41e8783978062fb79b671cabfba&imgtype=0&src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farchive%2Fbbe5dfc39f4cbdeccb027a834d6e0b921302545b.jpg);
  background-size: cover;
  /* background-repeat: no-repeat;
  background-position: center; */
  border-radius: 4px;
  overflow: hidden;
}

.sp-re-title{
  margin-top: 24px;
  height: 40px;
  line-height: 20px;
}
.sp-re-profile {
  position: absolute;
  bottom: 34px;
  left: 5px;
}
.sp-re-profile a{
  text-decoration: none;
  color: #222;
  transition: all 0.3s ease;
}
.sp-re-profile a:hover{
  color: #00a1d6;
}
.sp-re-profile>span{
  color: #aaa;
}
.sp-re-pic{
  display: inline-block;
  height: 45px;
  width: 45px;
  border-radius: 50%;
  border: 2px solid #fff;
  overflow: hidden;
}
.sp-re-pic img{
  height: 100%;
  width: 100%;
}
.sp-re-user{
  display: inline-block;
  padding-left: 5px;
  vertical-align: super;
  width: 68px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.sp-recommendation-pic{
  display: block;
  width:inherit;
  height: 150px;
  margin-top: 45px;
}
.sp-recommendation-pic img{
  width: 100%;
  height: 100%;
  border-radius: 4px;
}
</style>
