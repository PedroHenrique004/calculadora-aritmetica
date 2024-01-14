<script setup>
import {reactive} from 'vue'

const estado = reactive ({
  numero1: 0,
  numero2: 0,
  operacao: '+',
  resultado: '10',
})

const calcular = (estado) => {
  switch (estado.operacao) {
    case  '-':
      estado.resultado = estado.numero1 - estado.numero2
      break

    case  '*':
      estado.resultado = estado.numero1 * estado.numero2
      break

    case  '/':
      estado.resultado = estado.numero1 / estado.numero2
      break

    default:
      estado.resultado = estado.numero1 + estado.numero2
      break
  }
}


</script>

<template>
  <h1>{{ estado.resultado }}</h1>
  <div class="container d-flex justify-content-center align-items-center" style="height: 100vh;">
    <form class="w-50" v-on:submit.prevent="(evento)">
      <div class="input-group mb-3">
        <input type="number" class="form-control" placeholder="Digite um número" v-model="estado.numero1">
        <select class="form-select" v-model="estado.operacao">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">x</option>
          <option value="/">%</option>
        </select>
        <input v-model="estado.numero2" type="number" class="form-control" placeholder="Digite outro número">
      </div>
      <div class="d-grid gap-2">
        <button class="btn btn-primary" @click="calcular(estado)">Calcular</button>
      </div>
    </form>
  </div>

</template>

<style scoped>
h1 {
    color: white;
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
    background-color: blue;
    padding: 20px;
    margin: 10px;
    border-radius: 10px;
    box-shadow: 5px 5px 10px black;
}
</style>
