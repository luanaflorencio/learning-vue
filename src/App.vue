<template>
  <div id="app">
    <h1>ProgramaDEV</h1>
    <Linguagem linguagem="Python" descricao="Lorem Ipsum" criador="Guido van Rossum" ano="1989"/>
  </div>
  
</template>

<script>
import Linguagem from './components/Linguagem';

export default {
  name: 'App',
  components: {
    Linguagem
  }
}
</script>

<style>
</style>
