<template>
  <div>


    <div class="menu">
      <a v-for="tab in menus" :key="tab">{{ tab }}</a>
    </div>
  
    <div v-for="(a, i) in products" :key="i">
      <h4>{{a}}</h4>
      <p>{{price1}} 만원</p>
      <button v-on:click="report++">허위매물신고</button> <span>{{ report }}</span>
      <button @click="report+=1">허위매물신고</button> <span>{{ report }}</span>
      <button @click="increase()">허위매물신고</button> <span>{{ report }}</span>
    </div>


    <div >
      <h4>{{products[1]}}</h4>
      <p>{{price2}} 만원</p>
    </div>
  
    <div>
      <h4>{{products[2]}}</h4>
      <p>{{price2}} 만원</p>
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


      report: 0,
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동 원룸', '천호동 원룸', '잠실동 원룸']
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
