<template>
  <div id="app">
    <Resultado :resultado="estado.resultado" /> 
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
  </div>
</template>

<script>
import Resultado from './components/Resultado.vue'

export default {
  name: 'App',
  components: {
    Resultado
  },
  data() {
    return {
      estado: {
        numero1: 0,
        numero2: 0,
        operacao: '+',
        resultado: '0',
      }
    }
  },
  methods: {
    calcular(estado) {
      switch (estado.operacao) {
        case  '-':
          estado.resultado = Number(estado.numero1) - Number(estado.numero2)
          break

        case  '*':
          estado.resultado = Number(estado.numero1) * Number(estado.numero2)
          break

        case  '/':
          estado.resultado = Number(estado.numero1) / Number(estado.numero2)
          break

        default:
          estado.resultado = Number(estado.numero1) + Number(estado.numero2)
          break
      }
    }
  }
}
</script>