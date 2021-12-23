<template>
  <div class="padre">
    <div class="logo">
      <img src="./../../../public/koalimer-header.png" alt="">
    </div>
    <div class="login">
        <div class="empleado" v-if="change == true">
          <h3>Acceder al área de empleado</h3>
          <h5>Nombre de usuario:</h5>
          <input type="text" placeholder="Nombre de usuario" required>
          <h5>Pin:</h5>
          <input type="password" placeholder="contraseña" required>
          <p><button @click="$emit('changeLogin')"> Iniciar Sesión</button> </p>
            <div class="cambio">
              <button @click="change = false">Acceso empresa</button>
            </div>
        </div>
        <div>
        <div class="admin" v-if="change == false">
          <h3>Acceder a la zona de gestión</h3>
          <h5>Nombre de usuario:</h5>
          <input type="text" placeholder="Nombre de usuario">
          <h5>Contraseña:</h5>
          <input type="password" placeholder="contraseña">
          <p><button @click="$emit('changeLogin')"> Iniciar Sesión</button></p>
          <p>¿Aun no tienes cuenta? <a href="">Registrarse</a></p>
          <p>¿Has olvidado la contraseña? <a href="">Recuperar</a></p>
            <div class="cambio">
              <button @click="change = true">Acceso empleado</button>
            </div>
          </div>
        </div>
        <div>
        </div>
        <!-- <div class="cambio">
          <button @click="change = true">Acceso empleado</button>
          <button @click="change = false">Acceso empresa</button>
        </div> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data() {
    return {
      change: true,
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img{
   width: 250px;
    height: auto;
    margin: 10px;
}
a {
  color: #55b499;
}
input {
  width: 100%;
  border: 1px solid black;
  padding: 10px;
  border-radius: 5px;
}
input:focus {
    outline: none;
    border-color: #55b499;
    box-shadow: 0 0 10px #55b499;
}
button{
  background-color: #55b499;
  border: none;
  border-radius: 5px;
  color: white;
  padding: 8px 30px;
}
button:hover{
  cursor: pointer;
}
h5{
  text-align: left;
}

.padre {
  display: flex;
  background: linear-gradient(#0C6A50,#98DDCA);
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  padding-top: 100px;
  padding-bottom: 50px;
  min-height: 100vh;
}
.login{
  background: white;
  padding: 35px;
  border: 2px solid black;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content:center;
  flex-direction: column;
  box-shadow: 1px 1px 30px 1px rgba(92, 92, 92, 0.541);
}
.cambio button{
  margin: 10px
}
.logo{
  display: flex;
  flex-direction: row;
  align-items: center;
}

</style>
