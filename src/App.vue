<template>
  <div id="app">
    <h2>Calculadora Aritmética</h2>

    <input type="number" v-model.number="numero1" placeholder="Digite o primeiro número" />
    <input type="number" v-model.number="numero2" placeholder="Digite o segundo número" />

    <select v-model="operacao">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>

    <h3>Resultado: {{ resultado }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma'
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case 'soma':
          return this.numero1 + this.numero2;
        case 'subtracao':
          return this.numero1 - this.numero2;
        case 'multiplicacao':
          return this.numero1 * this.numero2;
        case 'divisao':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Divisão por zero!';
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
#app {
  text-align: center;
  max-width: 300px;
  margin: auto;
}
input,
select {
  margin: 5px;
}
</style>