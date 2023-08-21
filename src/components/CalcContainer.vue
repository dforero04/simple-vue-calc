<script setup>
import { ref } from 'vue'

const inputString = ref('')
const equation = ref('')

function handleClear() {
  inputString.value = ''
  equation.value = []
}

function handleClick(event) {
  equation.value += event.target.value
  inputString.value += event.target.value
}

function handleOperator(event) {
  equation.value += event.target.value
  inputString.value = ''
}

function handleEquals() {
  console.log(eval(equation.value));
  inputString.value = eval(equation.value)
}
</script>

<template>
  <div class="calc">
    <span class="title">Simple Vue Calculator</span>
    <div class="calc-container">
      <input class="number-input" v-model="inputString" />
      <div class="keypad">
        <div class="numbers">
          <button value="1" @click="handleClick">1</button>
          <button value="2" @click="handleClick">2</button>
          <button value="3" @click="handleClick">3</button>
          <button value="+" @click="handleOperator">+</button>
          <button value="4" @click="handleClick">4</button>
          <button value="5" @click="handleClick">5</button>
          <button value="6" @click="handleClick">6</button>
          <button value="-" @click="handleOperator">-</button>
          <button value="7" @click="handleClick">7</button>
          <button value="8" @click="handleClick">8</button>
          <button value="9" @click="handleClick">9</button>
          <button value="*" @click="handleOperator">x</button>
          <button value="0" @click="handleClick">0</button>
          <button @click="handleClear">Clear</button>
          <button value="/" @click="handleOperator">&#247;</button>
          <button @click="handleEquals">=</button>
        </div>
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

.title {
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
  height: 55px;
  line-height: 55px;
  text-align: right;
  margin: auto auto auto 10px;
  padding: 0 20px;
  border-radius: 10px;
}

.keypad {
  width: 90%;
  margin-left: 5%;
  margin-top: 40px;
}

.numbers {
  width: 100%;
  font-size: 0;
  text-align: center;
}

button {
  font-size: 24px;
  color: red;
  display: inline-block;
  width: 25%;
  text-align: center;
  margin-bottom: 25px;
}

.operators {
  width: 100%;
  display: flex;
  text-align: right;
  flex-direction: column;
}
</style>
