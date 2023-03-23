<template>
  <div>

    <div class="black-bg" v-if="modal == true" @click="modal = false">
      <div class="white-bg">
        <p>자세히 보기</p>
        <img :src="products[detail].image" class="small-img">
        <h4>{{ products[detail].title }}</h4>
        <p>{{ products[detail].content }}</p>

        <button @click="modal = false">창 닫기</button>
      </div> 
    </div>

    <div class="menu">
      <a v-for="tab in menus" :key="tab">{{ tab }}</a>
    </div>

    <DiscountBanner/>
  
    <div class="room" v-for="(room, i) in products" :key="i">
      <img :src="products[i].image">
      <h4 @click="modal=true; detail=i">{{ products[i].title }}</h4>
      <p>{{ products[i].content }}</p>
      <p class="gray">{{ products[i].price }}원</p>
      <button @click="products[i].report++">허위매물신고</button> <span>{{products[i].report }}</span>
    </div>

  </div>
</template>

<script>


import contents from './assets/js/content.js';
import DiscountBanner from './assets/component/DiscountBanner.vue';



export default {
  name: 'App',
  data() {
    return {
      report: [0,0,0],
      menus : ['Home', 'Shop', 'About'],
      products : contents,

      // 모달창
      detail: 0,
      modal: false
    }
  },
  components: {
    DiscountBanner : DiscountBanner,
  },

  methods : { 
    increase(){ 
      this.report += 1 
    }
  }
}
</script>

<style>
body {
  margin : 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
  margin-top: 50%;
} 

.room img {
  width: 85%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.gray {
  color: gray;
}

.small-img {
  width: 85%;
}
</style>
