<template>
  <div id="app">

    <h1>ProgramaDEV</h1>
    
    <h2>Cadastrar uma nova Linguagem</h2>

    Qual o nome da Linguagem? <br>
    <input type="text" placeholder="Nome"> <br>
    Fale um pouco sobre ela: <br>
    <input type="text" placeholder="Descrição"><br>
    Quem é o criador? <br>
    <input type="text" placeholder="Criador"><br>
    Ano de criação: <br>
    <input type="number" placeholder="Ano">

    <h2>Linguagens de Programação</h2>
  
    <div v-for="linguagem in linguagens" :key="linguagem.id">
      <Linguagem :linguagem="linguagem" :showcriador="true"/>
      <h3 class="edit">Editar:</h3>
      <input type="text" v-model="linguagem.nome">
      <input type="text" class= "edit2" v-model="linguagem.criador">
      <input type="number" class="edit3" v-model="linguagem.ano">
    </div>
  </div>
  
</template>

<script>
import Linguagem from './components/Linguagem';

export default {
  name: 'App',
  data() {
    return{
      boxProg: {
      nome: "Python",
      descricao: "Lorem Ipsum",
      criador: "Guido van Rossum",
      ano: 1989

      },
      linguagens: [
        {
          id: 1,
          nome: "Python",
          descricao: "Lorem Ipsum",
          criador: "Guido van Rossum",
          ano: 1989

        },
        {
          id: 2,
          nome: "JavaScript",
          descricao: "Ipsum Lorem",
          criador: "Brendan Eich",
          ano: 1995

        },
        {
          id: 3,
          nome: "PHP",
          descricao: "Lorem & Ipsum",
          criador: "Rasmus Lerdorf",
          ano: 1994

        }
      ]
    }
   
  },
  components: {
    Linguagem
  }
}
</script>

<style>
.edit2{
    margin-left: 1%;
}
.edit3{
   margin-left: 1%;
}
</style>
