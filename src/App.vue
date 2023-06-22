<template>
  <div id="nav">
    <RouterLink to="/">Home</RouterLink> |
    <RouterLink to="/about">About</RouterLink> 
   
    <!-- <RouterLink to="/hello">Hello</RouterLink> -->
  </div>
  <router-view/>
  <div class="footer">
    <p>Contact</p>
    <p>Ph:(401)-965-5309</p>
    <p><a href="https://github.com/sonu-cyber/weather-api-vue/" class="git_link">Github</a></p>
    <span><a href="https://www.linkedin.com/in/gayathriraghuram/" class="linked_link">LinkedIn</a></span>
  </div>
</template>

<script>
import { RouterLink, RouterView } from "vue-router";
export default {
  name: "App",
  data(){
    return{
     
    }
    
  }
  
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 50px;
  background-color:  #2c3e50;
  border-radius:8px;
  
}

#nav a {
  font-weight: bold;
  color: #4d6985;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
.footer{
  padding:70px;
  font-size:14px;
  background-color:  #2c3e50;
  color: whitesmoke;
  border-radius:8px;
}
.footer > p > .git_link{
  color: whitesmoke;
}
.footer > p > .linked_link{
  color:whitesmoke;
}
a{
  text-decoration:none;
  color:whitesmoke;
  
}
</style>
