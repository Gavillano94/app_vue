<template>
  <div>
    <div class="menu" >
      <div class="burguer" @click="showMenu = !showMenu">
        <i class="fas fa-bars fa-3x"></i>
      </div>
      <div class="logo">
        <!-- <img src="./../../public/koala.svg" alt="">
        <h1>Koalimer</h1> -->
        <img src="./../../public/koalimer-header.png" alt="">
      </div>
    </div>
    <div class="body">
      <div class="left-menu">
        <transition name="fade">
          <div class="left" v-if="showMenu">
            <h2 @click="selectTab = 'inicio'">Inicio</h2>
            <h2 @click="selectTab = 'calendario'">Calendario</h2>
            <h2>Usuario</h2>
            <h2 @click="$emit('backToLogin')">Cerrar sesión</h2>
          </div>
        </transition>
      </div>
      <div class="central-menu">
        <template v-if="selectTab == 'inicio'">
          <main-inicio></main-inicio>
        </template>
        <template v-else-if="selectTab == 'calendario'">
          <calendario></calendario>
        </template>

      </div>
    </div>
  </div>
</template>
<script>
import mainPageMenu from './mainMenu.vue'
import mainIncio from "./menu.vue"
import calendario from './calendario.vue'

export default {
  name: 'myPage',
  components: {
    'main-page-menu': mainPageMenu,
    'main-inicio': mainIncio,
    'calendario': calendario
  },
  data() {
    return {
      showMenu: false,
      selectTab: "inicio",
    }
  },
  created() {
    setInterval(this.getNow, 1000);
  }
}


</script>
<style>
  @import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css";

  .menu {
    width: 100%;
    height: 100px;
    background: #0C6A50;
    display: grid;
    grid-template-columns: 10% 80% 10%;
  }
  .burguer {
    width: 50px;
    height: 0px;
    margin: 25px;
    cursor: pointer;
    color: white;
  }
  .logo img{
    width: 250px;
    height: auto;
    margin-top: 10px;
  }
  .body{
    display: grid;
    grid-template-columns: 20% 60%;
    min-height: 100vh;
    background-image: url('./../../public/tree-wallpaper-opacity-20.png');
    background-size: cover;
    background-repeat: no-repeat;
  }
  .left-menu{
    display: flex;
    flex-direction: column;
    z-index: 2;
  }
  .time{
    font-size: 20px;
    height: 23px;;
  }
  .left {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    background: linear-gradient(#0C6A50,#98DDCA);
    width:300px;
    height: 100%;
    color:bl;
    text-align: left;
  }
  .left h2 {
    margin-left: 20px;
    width: auto;
    cursor: pointer;
  }
  .left h2:hover{
    text-shadow: #000 1px 3px 10px;
  }
  .left h2:active {
    color: black
  }
  .fade-enter-active, .fade-leave-active {
  transition: all .3s
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    width: 0px;
    color: transparent;
  }
</style>
