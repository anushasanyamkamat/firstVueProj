<template>
  <div id="app">
    <h1>Button Clicked Count:- {{btnCount}} </h1>
    <Counter  
      :defaultCount="-2" 
      :minCount="-4" 
      :maxCount="4" 
      v-on:btn-click="btnCount++"/>
    <Counter 
      :defaultCount="-2" 
      :minCount="-4" 
      :maxCount="4" 
      v-on:btn-click="btnCount++"/>
    <Counter 
      :defaultCount="-2" 
      :minCount="-4" 
      :maxCount="4" 
      v-on:btn-click="btnCount++"/>
  </div>
</template>

<script>
import Counter from './components/Counter.vue'

export default {
  name: 'App',
  components: {
    Counter
  },
  data: function(){
    return{
      btnCount: 0
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
</style>
