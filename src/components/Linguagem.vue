<template>
    <div>
        <h1>Linguagens de Programação</h1>
        Qual sua linguagem de programação do seu interesse?<br>
        <input type="text" placeholder="Ex: PHP" id="txt">
        <input type="submit" value="Procurar" id="btn">
        <input type="number" v-model="ano">

        <div class="data">
            <h4>Linguagem: {{ linguagem }}</h4>
            <hr>
            <h4>Descrião: {{ descricao }}</h4>
            <hr>
            <h4>Criador: {{ criador }}</h4>
            <hr>
            <h4>Ano de Criação: {{ ano }}</h4>
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
        linguagem: String,
        descricao: String,
        criador: String,
        ano: Number
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
</style>
