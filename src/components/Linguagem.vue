<template>
    <div>
        <h1>Linguagens de Programação</h1>
        Qual sua linguagem de programação do seu interesse?<br>
        <input type="text" placeholder="Ex: PHP" id="txt">
        <input type="submit" value="Procurar" id="btn">

        <div class="data">
            <h4>Linguagem: {{ linguagem.nome }}</h4>
            <hr>
            <h4 v-show="2 > 1">Descrião: {{ linguagem.descricao }}</h4>
            <hr>
            <h4 v-if="showcriador == true">Criador: {{ linguagem.criador }}</h4>
            <h4 v-else>Criador Desconhecido!</h4>
            <hr>
            <h4>Ano de Criação: {{ linguagem.ano }}</h4>
        </div>
    </div>
</template>

<script>
export default{
    data() {
        return{
            
        }
    },
     props: {
        description: Number,
        showcriador: Boolean,
        linguagem: Object,
        
    }
    
}
</script>

<style scoped>
#btn{
    background-color: #2760b4;
    color: white;
    width: 7%;
    height: 27px;
}

#txt{
    width: 20%;
    height:30px;
    margin-right: 1%;
}
.data{
    background-color:#6999e0; 
    width: 20%;
    padding: 1%;
    margin-top: 1%;
    margin-left: 1%;
}
.box-ano{
    margin-left: 1%;
}

</style>
