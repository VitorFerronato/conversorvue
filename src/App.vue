<template>
  <div id="app">
    <h1>Conversor de moedas</h1>
    <div class='container'>
      <ConversorApp  moeda-a='USD' moeda-b='BRL' />
      <ConversorApp  moeda-a='BRL' moeda-b='USD' />
      <ConversorApp  moeda-a='EUR' moeda-b='BRL' />
      <ConversorApp  moeda-a='BRL' moeda-b='EUR' />
    </div>

  </div>
</template>

<script>
import ConversorApp from './components/ConversorApp.vue'

export default {
  name: 'App',
  components: {
    ConversorApp
  }
}
</script>

<style>
  #app{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  .container{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 2rem;
    align-items: center;
    margin-top: 3rem;
  }
 
</style>
