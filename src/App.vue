<script setup>
import { reactive, computed } from 'vue'

const estado = reactive({
  num1: 0,
  num2: 0,
  operacao: '+',
});


const resultado = computed(() => {
  const { num1, num2, operacao } = estado
  
  switch (operacao) {
    case '+':
      return num1 + num2
    case '-':
      return num1 - num2
    case '*':
      return num1 * num2
    case '/':
      return num1 / num2
  }
})
</script>

<template>
  <div class="container">
    <div class="calculadora">
      <h1>Calculadora aritmética</h1>
      <label for="n1">Primeiro número</label>
      <input type="number" v-model.number="estado.num1" id="n1" />

      <label for="n2">Segundo número</label>
      <input type="number" v-model.number="estado.num2" id="n2" />

      <label for="text">Operações</label>
      <select v-model="estado.operacao">
        <option value="+">Adição (+)</option>
        <option value="-">Subtração (-)</option>
        <option value="*">Multiplicação (X)</option>
        <option value="/">Divisão (/)</option>
      </select>
      <div class="resul">
        <p id="resultado">Resultado: {{ resultado }}</p>
      </div>

      
    </div>
  </div>
</template>


<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


.calculadora {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  color: #ccc;
  background-color: #1f1f1f;
  padding: 2rem;
  border-radius: 5px;
  min-width: 30%;
  max-width: 30%;
  overflow: auto;
  gap: 1rem;
}

h1 {
  margin-bottom: 1rem;
  text-align: center;
}

input {
  padding: 8px 5px;
  outline: none;
  border-radius: 3px;
  width: 100%;
  background-color: #181818;
  color: #ccc;
  transition: .3s;
}

input:focus{
  border-color: #ccc;
}

.resul {
  position: relative;
  transform-style: preserve-3d;
}
.resul p {
  font-size: 32px;
  font-weight: bold
}

select {
  border-radius:3px;
  background-color: #181818;
  color: #ccc;
  border: 1px solid #17171A;
  padding: 8px 5px;
}




</style>
