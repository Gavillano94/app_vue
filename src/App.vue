<template>
  <div id="app">
    <div class="login" v-if="showLogin == false">
      <login v-on:changeLogin="showLogin = true"/>
    </div>
    <div class="main" v-if="showLogin == true">
      <mainPage/>
    </div>
  </div>
</template>

<script>
import login from './components/login/index.vue';
import mainPage from './components/mainPage.vue';

export default {
  name: 'App',
  components: {
    login,
    mainPage
  },
  data() {
    return {
      showLogin: false
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
  display: block;
  overflow: auto;
  min-height: 100vh;
}
/* html {
  background: #eeeeee;
} */
body{
  margin: 0px;
  height: 100%;
  width:100%;
}
@font-face {
  font-family: "clock-font";
  src: local("clock-font"),
   url(./assets/digital-7.ttf) format("truetype");
}
@font-face {
  font-family: "clock-fat-font";
  src: local("clock-fat-font"),
   url(./assets/digital-dream.fat.ttf) format("truetype");
}

</style>
