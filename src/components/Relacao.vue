<template>
  <div>
    <h1>Calculadora de Média</h1>
    <section id='inputs'>
      <label for="nome">Nome:</label>
      <input type="text" v-model="nome">
      
      <label for="nota1">Nota 1:</label>
      <input type="number" v-model="nota1" class="input">
      
      <label for="nota2">Nota 2:</label>
      <input type="number" v-model="nota2" class="input">
    </section>
    <!-- Botão para calcular -->
    <button v-on:click="calcularMedia">Calcular Média</button>
    
    <!-- Exibe a média e o status de aprovação -->
    <p v-if="media !== null">Média: {{ media }}</p>
    <p v-if="media !== null">{{ nome }} está {{ aprovado ? 'Aprovado' : 'Reprovado' }}</p>
  </div>
</template>

<script>
export default {
  name: Relacao,
  
  data() {
    return {
      nome: '',
      nota1: null,
      nota2: null,
      media: null,
      aprovado: false
    };
  },
  methods: {
    calcularMedia() {
      if (this.nota1 !== null && this.nota2 !== null) {

        this.media = (this.nota1 + this.nota2) / 2;
        
        this.aprovado = this.media >= 7;
      }
    }
  }
};
</script>

<style>
  #inputs{
    display: flex;
    flex-direction: column;
  }

  input{
    width: 400px;
  }

  .input{
    width: 100px;
  }
</style>