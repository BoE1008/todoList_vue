<template>
  <div id="app">
    <img src="./assets/logo.png">
    <component-a :sonmsg="msg" @childsend="showfromchild"></component-a>
  </div>
</template>

<script>
import componentA from './components/componentA';
export default {
  data(){
    return{
      msg:"父传子"
    }
  },
  components: {
    componentA
  },
  methods:{
    showfromchild(data){
      alert(data);
    }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
