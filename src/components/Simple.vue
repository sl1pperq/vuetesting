<script setup>
import '/src/assets/css/bootstrap.min.css';
import {ref} from "vue";

let one = ref(1)
let two = ref(1)

let result = ref(null)

function setOne(e, o = +e.target.value) {
  one.value = o;
  console.log(one.value, o)
}

function setTwo(e, t = +e.target.value) {
  two.value = t;
  console.log(two.value, t)
}


function plus() {
  result.value = one.value + two.value;
}

function minus() {
  result.value = one.value - two.value;
}

function multi() {
  result.value = one.value * two.value;
}

function divide() {
  result.value = one.value / two.value;
}


</script>

<template>
  <div class="card mt-3 rounded-4">
    <div class="card-body">

      <div class="row g-3">
        <div class="col-md-3">
          <label>Первое число</label>
          <input type="number" class="form-control rounded-4" :value="one" @change="setOne" />
        </div>
        <div class="col-md-3">
          <label>Второе число</label>
          <input type="number" class="form-control rounded-4" :value="two" @change="setTwo" />
        </div>
      </div>

      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="plus">
        Плюс
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="minus">
        Минус
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="multi">
        Умножить
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="divide">
        Делить
      </button>
      <button class="btn btn-danger mt-3 rounded-4 mx-1" v-if="result != null" @click="result=null; one=1; two=1">
        Очистить
      </button>
    </div>
  </div>

  <div class="card mt-3 rounded-4" v-if="result != null">
    <div class="card-body">
      <p class="card-text">Результат: {{ result }}</p>
    </div>
  </div>

</template>

<style scoped>

</style>