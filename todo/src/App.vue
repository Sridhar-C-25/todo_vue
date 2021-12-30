<template>

  
  <Header /> 
 <div class="control-btn-box"><button @click="back">Back</button>
  <button @click="forward">Forward</button>
  <button @click="redirect">Redirect</button></div>
  <router-view/>
  
</template>

<script>
import Header from './components/layout/Header.vue'
export default {
  name:'App',
  components:{
    Header
  },
  methods:{
    back(){
      this.$router.go(-1)
    },
    forward(){
      this.$router.go(1)
    },
    redirect(){
      this.$router.push({name : 'Home'})
    }
  }
}
</script>

<style>
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
}

#nav {
  padding: 25px;
  color: #999;

}

#nav a {
  font-weight: bold;
  color: #999;
  text-decoration: none;
  font-size: 1.2rem;
  text-transform: uppercase;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

button{
  border: 0;
  font-family: Poppins;
  padding: 6px 20px;
  background: #42b983;
  cursor:pointer;
  /* position: absolute; */
  /* top: 100px; */
  float: center;
  outline: none;
  right: 0;
  margin: 10px;
}

button:nth-child(2){
  right: 110px !important;
}

button:nth-child(3){
  right: 200px;
}
.control-btn-box{
  background: #222;
}

</style>
