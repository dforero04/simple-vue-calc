<script setup>
import { ref } from 'vue'

const inputNum = ref('')

function handleClick(event) {
  inputNum.value = event.target.value;
}

function handleAdd(event) {

}
</script>

<template>
  <div class="calc">
    <span class="title">Simple Vue Calculator</span>
    <div class="calc-container">
      <input class="calc-input" v-model="inputNum" placeholder="Enter calculation" />
      <div class="keypad">
        <button value=1 @click="handleClick">1</button>
        <button value=2 @click="handleClick">2</button>
        <button value=3 @click="handleClick">3</button>
        <button value=4 @click="handleClick">4</button>
        <button value=5 @click="handleClick">5</button>
        <button value=5 @click="handleAdd">+</button>
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
  color: #d1d1d1;
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
