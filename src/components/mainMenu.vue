<template>
  <div class="left">
    <h2>Inicio</h2>
    <h2>Calendario</h2>
    <h2>Usuario</h2>
    <h2>Cerrar sesión</h2>
  </div>
</template>

<script>
export default {
  name: 'main-page-menu',
}
</script>

<style>
  .left {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    background: #19B87C;
    width:300px;
    height: 100%;
    color:white;
    text-align: left;
  }
  .left h2 {
    margin-left: 20px;
    width: auto;
    cursor: pointer;
  }
  .left h2:hover{
    text-shadow: rgb(0, 0, 0) 1px 0 10px;
  }
</style>
