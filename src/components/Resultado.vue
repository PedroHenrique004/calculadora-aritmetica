<template>
    <h1>{{ resultado }}</h1>
  </template>
  
  <script>
  export default {
    name: 'Resultado',
    props: {
      resultado: {
        type: Number,
        required: true
      }
    }
  }
  </script>
  
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