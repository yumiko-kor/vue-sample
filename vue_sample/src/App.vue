<template>
  <div>

    <!-- <div class="black-bg" v-if="modal == true">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>Information Text</p>
        <button @click="modal = false">창 닫기</button>
      </div> 
    </div> -->

    <div class="black-bg" v-if="modal == true">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>Information Text</p>
        <button @click="modal = false">창 닫기</button>
      </div> 
    </div>


    <div class="menu">
      <a v-for="tab in menus" :key="tab">{{ tab }}</a>
    </div>
  
    <div class="room" v-for="(room, i) in products" :key="i">
      <img :src="products[i].image">
      <h4 @click="modal=true">{{ products[i].title }}</h4>
      <p>{{ products[i].content }}</p>
      <p class="gray">{{ products[i].price }}원</p>
      <button @click="products[i].report++">허위매물신고</button> <span>{{products[i].report }}</span>
    </div>

  </div>
</template>

<script>


import contents from './assets/js/content.js';



export default {
  name: 'App',
  data() {
    return {
      report: [0,0,0],
      menus : ['Home', 'Shop', 'About'],
      products : contents,

      // 모달창
      modal: false
    }
  },
  components: {
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

</style>
