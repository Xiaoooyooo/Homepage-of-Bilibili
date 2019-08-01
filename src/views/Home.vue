<template>
  <div class="home">
    <main-nav></main-nav>
    <div class='container'>
    <recommend/>
    <spread/>
    <ad imgsrc='https://i0.hdslb.com/bfs/sycp/creative_img/201907/e9c005fb1af07d30c94e7ab1bf3c8ab4.jpg'/>
    <live/>
    <cartoon/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import mainNav from '../components/header/header.vue';
import recommend from '../components/recommend/recommend.vue';
import spread from '../components/spread/spread.vue';
import live from '../components/live/live.vue'
import ad from '../components/common/ad'
import cartoon from '../components/cartoon/cartoon'
export default {
  name: 'home',
  components: {
    // HelloWorld,
    mainNav,
    recommend,
    spread,
    live,
    ad,
    cartoon
  }
}
</script>
<style scoped>
.container{
  width:1160px;
  min-width: 960px;
  margin: 0 auto;
}
</style>
