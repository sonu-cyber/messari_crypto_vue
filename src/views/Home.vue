<template>
  <div class="home">
    <Hello msg="A Crypto currency website in Vue.js" />
  </div>
</template>

<script>
// @ is an alias to /src
import Hello from "@/components/Hello.vue";

export default {
  name: "Home",
  components: {
    Hello,
  },
};
</script>
<style scoped>

.home {
  display: flexbox;
  justify-content:center;
  flex-direction: column;
  color:#2c3e50;
  width:100vw;
  
  }
</style>