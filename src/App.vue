<template>
  <div id="app">
    <caixas :caixinhas="caixinhas"/> 
    <ferramentas :caixinhas="caixinhas" @alteraCor="alteraCor($event)" @alterouTexto="alteraTexto($event)"/>
  </div>
</template>

<script>
import Caixas from "./components/Caixas.vue"
import Ferramentas from "./components/Ferramentas.vue"
export default {
  name: 'App',
  components: {  
    Caixas, Ferramentas 
  }, data: function(){
    return{
      caixinhas: [{
        titulo: "1",
        cor: "background: blue"
      },{
        titulo: "2",
        cor: "background: yellow"
      },{
        titulo: "3",
        cor: "background: red"
      }]
    }
  }, methods: {
    alteraCor: function(event){
      this.caixinhas[event.caixa].cor = event.cor
    }, alteraTexto: function(event){
       this.caixinhas[event.caixa].titulo = event.titulo
    }
  }
}
</script>

<style>
</style>