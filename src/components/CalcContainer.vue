<script setup>
import { ref } from 'vue'

const inputString = ref('')
const inputNumbers = ref([])
const inputOperators = ref([])

function handleClear() {
  inputString.value = ''
  inputNumbers.value = [];
  inputOperators.value = [];
}

function handleNumbers(event) {
  inputNumbers.value.push(event.target.value);
}

function handleOperators(event) {
  inputOperators.value.push(event.target.value)
}

function handleEquals() {
  console.log("numbers: ", inputNumbers.value);
  console.log("operators: ", inputOperators.value);

  if (inputOperators.value.length >= inputNumbers.value.length) {
    alert('Equation cannot end with an operator.');
  } else if (inputNumbers.value.length === 1) {
    inputString.value = inputNumbers.value;
  } else {
    let answer = Number(inputNumbers.value[0]);
    for (let i = 1; i < inputNumbers.value.length; i++) {
      if (inputOperators.value[i - 1] === '+') {
        answer += Number(inputNumbers.value[i])
      }
    }
    inputString.value = answer;
  }
}
</script>

<template>
  <div class="calc">
    <span class="title">Simple Vue Calculator</span>
    <div class="calc-container">
      <input class="calc-input" v-model="inputString" placeholder="Enter calculation" />
      <div class="keypad">
        <button @click="handleClear">Clear</button>
        <button value="1" @click="handleNumbers">1</button>
        <button value="2" @click="handleNumbers">2</button>
        <button value="3" @click="handleNumbers">3</button>
        <button value="4" @click="handleNumbers">4</button>
        <button value="5" @click="handleNumbers">5</button>
        <button value="+" @click="handleOperators">+</button>
        <button @click="handleEquals">=</button>
      </div>
    </div>
  </div>
</template>

<style>
.calc {
  width: 350px;
  margin: 40px auto 0 auto;
  position: relative;
}

.calc span.title {
  font-weight: 700;
  letter-spacing: 2px;
  display: block;
  text-align: center;
}

.calc-container {
  margin-top: 30px;
  width: 100%;
}

input {
  font-size: 20px;
  color: blue;
  width: 80%;
  font-weight: 400;
}

input .calc-input {
  height: 55px;
  line-height: 55px;
  text-align: right;
  padding: 0 20px;
  border-radius: 10px;
}

.keypad {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
