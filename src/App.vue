<script setup>
import { reactive } from 'vue';

const state = reactive({
  num1: 0,
  num2 : 0,
  conta: '',
  resultado: '',
})

function somar(num1, num2) {
  state.resultado = num1 + num2
}

function subtratir(num1, num2) {
  state.resultado = num1 - num2
}

function multiplicar(num1, num2) {
  state.resultado = num1 * num2
}

function dividir(num1, num2) {
  state.resultado = num1 / num2
}

</script>

<template>
  <body>
    <header class="col-md-12 text-center pt-3">
    <h1>Calculadora com Vue</h1>
  </header>
  <main>
    <form class="row d-block text-center my-auto" >
      <label class="col-md-6" for="num1">Numero 1</label>
      <input class="col-md-6" v-model="state.num1" type="number" id="num1" placeholder="insira o 1o numero">
      <label class="col-md-6" for="num2">Numero 2</label>
      <input class="col-md-6" v-model="state.num2" type="number" id="num2" placeholder="insira o 2o numero">
      <div class="row">
        <select v-model="state.conta" class="col-md-4 text-center mx-auto" >
          <option value="somar">+</option>
          <option value="subtratir">-</option>
          <option value="multiplicar">*</option>
          <option value="dividir">/</option>
        </select>
      </div>
      <div class="row mt-3">
        <p v-if="state.conta === 'somar'"> {{ somar(state.num1, state.num2) }} {{ state.resultado }} </p>
        <p v-else-if="state.conta === 'subtratir'"> {{ subtratir(state.num1, state.num2) }} {{ state.resultado }}</p>
        <p v-else-if="state.conta === 'multiplicar'"> {{  multiplicar(state.num1, state.num2) }}{{ state.resultado }} </p>
        <p v-else-if="state.conta === 'dividir'"> {{ dividir(state.num1, state.num2) }} {{ state.resultado }}</p>
      </div>
    </form>
  </main>
  </body>
</template>

<style scoped>
  body {
    background-color: rgb(130, 128, 128);
  }
</style>
