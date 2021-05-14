<template>
  <div id="app">

    <h1>ProgramaDEV</h1>
    
    <h2>Cadastrar uma nova Linguagem</h2>

    Qual o nome da Linguagem? <br>
    <input type="text" placeholder="Nome" v-model="nomeField"> <br>
    Fale um pouco sobre ela: <br>
    <input type="text" placeholder="Descrição" v-model="descricaoField"><br>
    Quem é o criador? <br>
    <input type="text" placeholder="Criador" v-model="criadorField"><br>
    Ano de criação: <br>
    <input type="number" placeholder="Ano" v-model="anoField">
    <button @click="novaLinguagem" id="btn">Cadastrar</button><br>
    <small v-show="invalid" class="erro">Campo de nome e/ou descrição inválido ou não preenchido!</small>

    <h2>Linguagens de Programação</h2>
  
    <div v-for="linguagem in linguagens" :key="linguagem.id">
      <Linguagem :linguagem="linguagem" :showcriador="true" @deletando="deletandoLinguagem($event)"/>
      <!-- <h3 class="edit">Editar:</h3>
      <input type="text" v-model="linguagem.nome">
      <input type="text" class= "edit2" v-model="linguagem.criador">
      <input type="number" class="edit3" v-model="linguagem.ano"> -->
    </div>
  </div>
  
</template>

<script>
import Linguagem from './components/Linguagem';

export default {
  name: 'App',
  data() {
    return{
      invalid: false,
      nomeField: "",
      descricaoField: "",
      criadorField: "",
      anoField: 0,

      linguagens: [
        {
          id: 3,
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
          id: 5,
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
  },
  methods: {
    novaLinguagem: function(){
      if(this.nomeField == "" || this.nomeField.length < 2 || this.descricaoField == "" || this.descricaoField.length < 6){
        this.invalid= true;
      }
      else{
      this.linguagens.push({nome: this.nomeField, descricao: this.descricaoField, criador: this.criadorField, ano: this.anoField, id: Date.now()});
      this.nomeField= "";
      this.descricaoField= "";
      this.criadorField= "";
      this.anoField= 0;
      this.invalid= false;
      }
      
    },
    deletandoLinguagem: function($event) {
      var id = $event.idLinguagem;
      var reloadArray = this.linguagens.filter(linguagem => linguagem.id != id);
      this.linguagens = reloadArray;
    }
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
#btn{
    background-color: #2760b4;
    color: white;
    width: 7%;
    height: 27px;
    margin-left:1%;
}
.erro{
  color:red;
}
</style>
