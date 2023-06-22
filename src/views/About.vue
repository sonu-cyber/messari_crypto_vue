<template>
  <div class="about">
    
   <h3>About Page</h3>
    <div class="info">
      <p>
        This <b>Vue app</b> uses <b>fetch API</b> to get data from the Messari Crypto website.
      </p>
      <p>
        It uses <b>Vue routing</b> to send data from components to different routes.
      </p>
      <p>
        The <b>data from</b> the Messari Crypto website is displayed on the screen.
      </p>
      <p>
        <b>Flexbox</b> is used to generate a <b>Responsive web page</b>
      </p>
  
      
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.about {
  display: flexbox;
  justify-content:center;
  flex-direction: column;
  color:#2c3e50;
  height:100vh;
  width:100vh;
  
}
h3{
  padding-top:25px;
  margin-left:350px;
  justify-content:center;
  color:#230939;
}
p{
  text-align: left;
  font-size:16px;
  line-height:28px;
}
 .info{
  color:#230939;
  padding: 30px;
}
</style>
