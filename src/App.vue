<template>
  

  <div id="appVue" class="bg-dark">
    <nav id="empresa" class="d-flex justify-content-between py-1 mb-2 align-items-center">
      <small class="fs-6">Games Opinion</small>
      <router-link class="colorHome" to="/">Home</router-link>
    </nav>
    
    <router-view/>
  </div>

</template>



<script>

  export default{
    name: 'appVue',
    data: function(){
      return{

      }
    },
    data: function(){
      return{
        
      }
    },
    methods: {

    }


  }



</script>

<style scoped>


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

#empresa{
  background-color: black;
  color: white;
  
}
.colorHome{
  color:rgba(255, 255, 255, 0.932)!important;
  text-decoration: none;
}

</style>
