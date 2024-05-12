<script setup>
import '/src/assets/css/bootstrap.min.css';
import {ref} from "vue";

let num = ref(1)
let result = ref(null)

function setNum(e, o = +e.target.value) {
  num.value = o;
  console.log(num.value, o)
}

function sin() {
  result.value = Math.sin(num.value).toFixed(2);
}

function cos() {
  result.value = Math.cos(num.value).toFixed(2);
}

function tan() {
  result.value = Math.tan(num.value).toFixed(2);
}

function sqrt() {
  result.value = Math.sqrt(num.value).toFixed(2);
}

function fact() {
  result.value = factorial(num.value);
}


function factorial(n) {
  return (n !== 1) ? n * factorial(n - 1) : 1;
}

</script>

<template>
  <div class="card mt-3 rounded-4">
    <div class="card-body">

      <div class="row g-3">
        <div class="col-md-3">
          <label>Число</label>
          <input type="number" class="form-control rounded-4" :value="num" @change="setNum" />
        </div>
      </div>

      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="sin">
        Синус
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="cos">
        Косинус
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="tan">
        Тангенс
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="sqrt">
        Корень
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="fact">
        Факториал
      </button>
      <button class="btn btn-danger mt-3 rounded-4 mx-1" v-if="result != null" @click="result=null; num=1">
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