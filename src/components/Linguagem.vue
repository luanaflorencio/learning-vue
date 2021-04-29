<template>
    <div>
        <h1>Linguagens de Programação</h1>
        Qual sua linguagem de programação do seu interesse?<br>
        <input type="text" placeholder="Ex: Python" id="txt">
        <input type="submit" value="Procurar" id="btn">
        <input type="number" v-model="ano">
        {{ criador }}, {{ ano }}, {{ descrição }}
    </div>
</template>

<script>
export default{
    data() {
        return{
            
        }
    },
    props: {
        descrição: String,
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
</style>
