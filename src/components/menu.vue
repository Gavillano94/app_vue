<template>
  <div>
    <div class="clock">
      <h2>{{ timestamp }}</h2>
    </div>
    <div class="core">
      <div class="boton-hora">
        <div class="boton" @click="start = !start; getTime()">
          <template v-if="start == false">
            <i class="fas fa-sign-in-alt"></i>
            Fichar
          </template>
          <template v-else-if="start == true">
            <i class="fas fa-sign-out-alt"></i>
            Detener
          </template>
        </div>
        <div>{{timeSingUp}}</div>
      </div>
      <div class="boton-hora">
        <div class="boton" @click="changeButtonPause(); pauseTime()">
          <template v-if="pause == false">
            <i class="fas fa-pause"></i>
            Pausar
          </template>
          <template v-else-if="pause == true">
            <i class="fas fa-play"></i>
            Reanudar
          </template>
        </div>
        <div>{{timePause}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "menu-inicio",
  data() {
    return {
      timestamp: "",
      timeSingUp: null,
      timePause: null,
      start: false,
      pause: false,
    }
  },
  created() {
    setInterval(this.getNow, 1000);
  },
  methods: {
    getNow: function() {
      const today = new Date();
      //const date = today.getFullYear()+'-'+(today.getMonth()+1)+'-'+today.getDate();
      //const time = today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds();

      /* ######## Añadir 0 cuando el digito es menor de 10 para que mantenga la forma ########### */
      const time = (today.getHours() < 10 ? "0" + today.getHours() + ":": today.getHours() + ":") + (today.getMinutes() < 10 ?  "0" + today.getMinutes() + ":" : today.getMinutes() + ":") + (today.getSeconds() < 10 ? "0" + today.getSeconds()  : today.getSeconds());
      //const dateTime = date +' '+ time;
      this.timestamp = time;
    },
    getTime: function() {
      if (this.timeSingUp == null) {
        this.timeSingUp = this.timestamp
      }else{
        this.timeSingUp = null;
        this.timePause = null;
        this.pause = false
      }
    },
    pauseTime: function() {
      if (this.timePause == null && this.timeSingUp != null) {
        this.timePause = this.timestamp
      }else if (this.timePause != null) {
        this.timePause = null
      }
    },
    changeButtonPause: function() {
      if (this.timeSingUp != null && this.timePause == null) {
        this.pause = true
      }else{
        this.pause = false
      }
    }
  }
}
</script>

<style>
  .core {
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .clock{
    display: flex;
    align-items: center;
    justify-content: center;
    color:#033F2F;
    height: 100px;
    font-family: "clock-fat-font";
    font-size: 20px;
  }
  .clock h2{
    display: flex;
    align-items: center;
    justify-content: center;
    width: 200px;
    height: 40px;
    padding: 10px;
    border: 3px solid #033F2F;
    border-radius: 10px;
  }
    .boton {
      background: #0C6A50;
      color: white;
      width: 300px;
      margin: 20px;
      border-radius: 5px;
      font-size: 45px;
      display: grid;
      grid-template-columns: 20% 60%;
    }
    .boton i {
      margin: 5px;
    }
    .boton-hora{
      height:300px;
    }
    .boton:hover{
    cursor: pointer;
    }
</style>
