<template>
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
        <button class="btn btn-primary" @click="$emit('calcular', estado)">Calcular</button>
      </div>
    </form>
  </template>
  
  <script>
  export default {
    name: 'Formulario',
    props: {
      estado: {
        type: Object,
        required: true
      }
    }
  }
  </script>
  