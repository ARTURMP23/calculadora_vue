<template>
    <div>
      <h1>Calculadora</h1>
      <input type="number" v-model="numero1" @input="calcular">
      <select v-model="operacao" @change="calcular">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
      <input type="number" v-model="numero2" @input="calcular">
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        numero1: 0,
        numero2: 0,
        operacao: 'soma',
        resultado: 0
      };
    },
    methods: {
      calcular() {
        switch (this.operacao) {
          case 'soma':
            this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
            break;
          case 'subtracao':
            this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
            break;
          case 'multiplicacao':
            this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
            break;
          case 'divisao':
            this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
            break;
          default:
            this.resultado = 0;
        }
      }
    }
  };
  </script>
  
  