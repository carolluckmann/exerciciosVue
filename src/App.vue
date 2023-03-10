<script setup>
import {ref} from 'vue'
    const nome = 'Carolina'
    const idade = 18
    let valor1 = ref(0);  
    let valor2 = ref(0);
    let valor3 = ref(0);
    const ok = false;

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }
    function mostraDobro() {
        return `O dobro de ${valor1.value} é ${valor1.value * 2}.` 
    }
    function soma() {
      return `A soma de ${valor2.value} e ${valor3.value} é ${(valor2.value * 1) + (valor3.value)*1}`
    }
    
    function par(){
      if (soma() % 2 === 0){
        return `A soma é par`
      }
      }
    
</script>

<template>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ (inverter(nome)).toUpperCase() }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
        <hr>
        <input v-model="valor1">
        <p> {{ mostraDobro() }}</p>
        <hr>
        <input v-model="valor2">
        <input v-model="valor3">
        <p>{{ soma() }}</p>
        <div v-if="ok">
          <p>{{ par() }}</p>
        </div>
    </div>
</template>

<style scoped>
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>