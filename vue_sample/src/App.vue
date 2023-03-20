<template>
  <div>

    <div class="black-bg" v-if="modal == true" @click="modal = false">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>Information Text</p>
      </div> 
    </div>

    <div class="menu">
      <a v-for="tab in menus" :key="tab">{{ tab }}</a>
    </div>
  
    <div class="room">
      <img src="./assets/room/room0.jpg">
      <h4 @click="modal=true">{{ products[0] }}</h4>
      <p>{{price1}} 만원</p>
      <button @click="report[0]++">허위매물신고</button> <span>{{ report[0] }}</span>
    </div>
    

    <div class="room">
      <img src="./assets/room/room1.jpg">
      <h4>{{ products[1] }}</h4>
      <p>{{price1}} 만원</p>
      <button @click="report[1]++">허위매물신고</button> <span>{{ report[1] }}</span>
    </div>

    <div class="room">
      <img src="./assets/room/room2.jpg">
      <h4>{{ products[2] }}</h4>
      <p>{{price1}} 만원</p>
      <button @click="report[2]++">허위매물신고</button> <span>{{ report[2] }}</span>
    </div>


  </div>
</template>

<script>









export default {
  name: 'App',
  data() {
    return {
      price1 : 60,
      price2 : 90,


      report: [0,0,0],
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동 원룸', '천호동 원룸', '잠실동 원룸'],

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

</style>
