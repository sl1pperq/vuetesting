<script setup>
import '/src/assets/css/bootstrap.min.css';
import {ref} from "vue";

let num = ref(1);
let startBase = ref(2);
let endBase = ref(10);

let result = ref(null);

function setNum(e, o = +e.target.value) {
  num.value = o;
  console.log(num.value, o);
}

function setStartBase(e, t = +e.target.value) {
  startBase.value = t;
  console.log(startBase.value, t);
}

function setEndBase(e, b = +e.target.value) {
  endBase.value = b;
  console.log(endBase.value, b);
}

function convertBase(number, fromBase, toBase) {
  const parsedNumber = parseInt(number, fromBase);
  return parsedNumber.toString(toBase);
}

function convertNum() {
  result.value = convertBase(num.value, startBase.value, endBase.value);
}

</script>

<template>
  <div class="card mt-3 rounded-4">
    <div class="card-body">

      <div class="row g-3">
        <div class="col-md-4">
          <label>Число</label>
          <input type="number" class="form-control rounded-4" :value="num" @change="setNum" />
        </div>
        <div class="col-md-2">
          <label>Начальная система</label>
          <input type="number" class="form-control rounded-4" :value="startBase" @change="setStartBase" />
        </div>
        <div class="col-md-2">
          <label>Конечная система</label>
          <input type="number" class="form-control rounded-4" :value="endBase" @change="setEndBase" />
        </div>
      </div>

      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="convertNum">
        Перевести
      </button>
      <button class="btn btn-danger mt-3 rounded-4 mx-1" v-if="result != null" @click="result=null; num=1; startBase=2; endBase=10">
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