<template>
    <li class="vedio-items">
        <a class="item" href="javascript:;">
        <div class="mask">
          <img :src="background" alt="">
            <div class="info">
                <p>{{item.duration}}</p>
                <a href="javascript:;" title="稍后再看"></a>
            </div>
        </div>
        <div class='item-details'>
            <p class="item-title">{{item.title}}</p>
            <div v-if='showTab' class='item-info'>
                <div>
                  <i class='blbl-icon vedio-log vedio-play'></i>
                  <span>20.0万</span>
                </div>
                <div>
                  <i class='blbl-icon vedio-log vedio-danmu'></i>
                  <span>999</span>
                </div>
            </div>
        </div>
        </a>
    </li>
</template>
<script>
export default {
    props:{
        item:{
            type:Object,
            default(){
                return{
                    duration:'04:23',
                    title:'一些文字描述一些文字描述一些文字描述一些文字描述'
                }
            }
        },
        showTab:{
            type:Boolean,
            default(){
                return false
            }
        },
        background:{
          type:String,
          default(){
            return 'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3668167685,567077787&fm=26&gp=0.jpg'
          }
        }
    }
}
</script>

<style scoped>
.vedio-items {
  height: 150px;
  width: 160px;
  overflow: hidden;
}
.item {
  text-decoration: none;
  height: 100%;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}
.mask {
  position: relative;
  flex-shrink: 0;
  height: 100px;
  width: 160px;
  border-radius: 4px;
  overflow: hidden;
}
.mask img{
  position: absolute;
  width: 100%;
  height: 100%;
}
.info {
  opacity: 0;
  background: rgba(0, 0, 0, 0.2);
  height: 100%;
  width: 100%;
  position: relative;
  transition: all 0.3s ease;
}
.item:hover .info {
  opacity: 1;
}
.info p {
  color: #fff;
  position: absolute;
  bottom: 2px;
  left: 6px;
}
.info a {
  display: block;
  position: absolute;
  right: 6px;
  bottom: 4px;
  height: 22px;
  width: 22px;
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABYAAAAWCAYAAADEtGw7AAABT0lEQVQ4je3VMYrCQBTG8b/DWASLNKJgJ1hY2sloZeF2gkeYW+wZvIVXsLBJY5UdtLJLk17EIghCwChukWRxFzSaaLdfMwm8/EgemTclgOl02gEmwAAoky8RsAA+tdbrUoJ+AVZO8G9CoCeJ39Sq1+sopbBtO5e23+8xxrDdbi1gIog/vxAKYNs2Sqn0diBIenoP9X2fIAgyccv66WZZZBXvdjtc18UYkwlfJxM+n8+/1pfBefMPPw4LEZcEQcBqteJ0Or0GrlartFotLpcLnucxm83YbDbFYSEE/X6f4XBIpVLhcDjgOA6u63I8HvPDaRqNBuPxmHa7DcS7cT6f36yXj8IAUkq63S7NZpPlcomUtx9/Ck5Tq9UYjUZ3a976u0UQz9OiCcMwvYwk8XHyYYxBKXU9+p5Grybg4m1Hk9Bar4Ee4JC0JWeixOhprdffE/1yRW/TLMYAAAAASUVORK5CYII=);
}
.item-details{
    width: 100%;
    position: relative;
    line-height: 20px;
}
.item-title {
  height: 40px;
  color: #222;
  overflow: hidden;
  transition: color 0.5s ease;
}
.item:hover .item-title {
  color: #00a1d6;
}
.item-info{
    position: absolute;
    bottom: 0;
    width:100%;
    background-color: #fff;
    color:#9ba3ab;
    transition: all 0.3s ease;
}
.vedio-items:hover .item-info{
  bottom: -100%;
}
.item-info div{
  display: inline-block;
  width: 50%;
}
.vedio-log{
  display: inline-block;
  height: 12px;
  width: 12px;
  margin-right: 5px;
}
.vedio-play{
  background-position: -282px -90px;
}
.vedio-danmu{
  background-position: -282px -218px;
}
</style>
