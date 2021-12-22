<template>
  <div>
    <div class="box-flexible">
      <h1>Diciembre 2021</h1>
      <ol class="mobile tablet desktop">
        <li class="day-name">Lunes</li>
        <li class="day-name">Martes</li>
        <li class="day-name">Miércoles</li>
        <li class="day-name">Jueves</li>
        <li class="day-name">Viernes</li>
        <li class="day-name">Sábado</li>
        <li class="day-name">Domingo</li>
        <li class="prev">29</li>
        <li class="prev">30</li>
        <li class="first-day day">
          1
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          2
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          3
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="dias-festivos">4</li>
        <li class="dias-festivos">5</li>
        <li class="day">
          6
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          7
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          8
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          9
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          10
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="dias-festivos">11</li>
        <li class="dias-festivos">12</li>
        <li class="day">
          13
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          14
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="ausencia">
          15
          <p>Ausencia</p>
        </li>
        <li class="day">
          16
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          17
          <p class="turno">6:00h - 14:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="dias-festivos">18</li>
        <li class="dias-festivos">19</li>
        <li class="day">
          20
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          21
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          22
          <p class="turno">14:00h - 22:00h</p>
          <p class="horas-fichadas">8h</p>
        </li>
        <li class="day">
          23
          <p class="turno">14:00h - 18:00</p>
          <p class="horas-fichadas">4h</p>
        </li>
        <li class="dias-festivos">24</li>

        <li class="dias-festivos">25</li>
        <li class="dias-festivos">26</li>
        <li class="dias-festivos">27</li>
        <li class="dias-festivos">28</li>
        <li class="dias-festivos">29</li>
        <li class="dias-festivos">30</li>
        <li class="dias-festivos">31</li>
        <li class="next">1</li>
        <li class="next">2</li>
      </ol>

      <div class="horas">
        Horas totales al mes = <span id="totalHours"></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "calendario",
}
</script>

<style>
/* div {
  box-sizing: border-box;
  text-align: center;
  width: 80%;
  max-width: 81em;
  margin: 65px auto;
} */
@media screen and (max-width: 800px) {
  .box-flexible {
    width: 100%;
  }
}
ol {
  list-style: none;
  display: grid;
  gap: 5px;
  grid-template-columns: repeat(7, 1fr);
  padding: 0;
  margin-top: 75px;
}
li {
  text-align: right;
  padding: 15px 32px;
  height: 90px;
  border-radius: 10px;
}

li p {
  display: none;
  font-size: 14px;
}

p:first-child {
  display: block;
}

li:hover p {
  display: block;
}

.first-day {
  grid-column-start: 3;
}
.day-name {
  background-color: rgb(230, 230, 230);
  font-weight: bold;
  text-align: center;
  padding: 16px;
}
.turno {
  font-weight: 9px;
}
.horas-fichadas {
  text-align: center;
  background-color: #64d3a9;
}
.dias-festivos {
  background-color: #fbaeab;
}
.day {
  background-color: #abe2cd;
  font-size: 18px;
}
.ausencia {
  text-align: center;
  background-color: #14b6e8;
}
.horas {
  text-align: center;
  margin: 30px auto;
}
#totalHours {
  background-color: #64d3a9;
}
li.prev,
li.next {
  color: rgb(184, 175, 175);
}

</style>
