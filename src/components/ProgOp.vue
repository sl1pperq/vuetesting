<script setup>
import '/src/assets/css/bootstrap.min.css';
import {ref} from "vue";

let one = ref(1)
let two = ref(1)
let base = ref(2)

let result = ref(null)

function setOne(e, o = +e.target.value) {
  one.value = o;
  console.log(one.value, o)
}

function setTwo(e, t = +e.target.value) {
  two.value = t;
  console.log(two.value, t)
}

function setBase(e, b = +e.target.value) {
  base.value = b;
  console.log(base.value, b)
}

function sumInBase(num1, num2, base) {
  const sum = parseInt(num1, base) + parseInt(num2, base);
  return sum.toString(base);
}

function minInBase(num1, num2, base) {
  const sum = parseInt(num1, base) - parseInt(num2, base);
  return sum.toString(base);
}

function umnInBase(num1, num2, base) {
  const sum = parseInt(num1, base) * parseInt(num2, base);
  return sum.toString(base);
}

function delInBase(num1, num2, base) {
  const sum = parseInt(num1, base) / parseInt(num2, base);
  return sum.toString(base);
}

function plusNums() {
  result.value = sumInBase(one.value, two.value, base.value)
}

function minusNum() {
  result.value = minInBase(one.value, two.value, base.value)
}

function multiNum() {
  result.value = umnInBase(one.value, two.value, base.value)
}

function divideNum() {
  result.value = delInBase(one.value, two.value, base.value)
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
        <div class="col-md-2">
          <label>Система счисления</label>
          <input type="number" class="form-control rounded-4" :value="base" @change="setBase" />
        </div>
      </div>

      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="plusNums">
        Плюс
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="minusNum">
        Минус
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="multiNum">
        Умножить
      </button>
      <button class="btn btn-warning mt-3 rounded-4 mx-1" @click="divideNum">
        Делить
      </button>
      <button class="btn btn-danger mt-3 rounded-4 mx-1" v-if="result != null" @click="result=null; one=1; two=1; base=2">
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