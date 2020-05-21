<template>
  <div id="ferramentas">
      <select v-model="caixaSel">
          <option value="" selected disabled>Selecione uma caixa</option>
          <option v-for="(caixa, index) in caixinhas" :key="index" :value="index">
              {{caixa.titulo}}
          </option>
      </select>
        
        <div id="paleta">
            <div class="cor" :style="cor" v-for="(cor, index) in cores" :key="index" @click="alteraCor(cor)"></div>
        </div>
        <div class="nomeCaixa">
            <input type="text" placeholder="Digite o nome da caixa" v-model="titulo">
            <button @click="alterarTexto">Ok</button>
        </div>

  </div>
</template>

<script>
export default {
    name: "Ferramentas",
    props: ['caixinhas'],
    data: function(){
        return{
            cores: ['background: orange', 'background: white', 'background: green'],
            caixaSel: '',
            titulo: ''
        }
    }, methods:{
        alteraCor: function(cor){
            this.$emit('alteraCor', {
                cor: cor,
                caixa: this.caixaSel
            })
        }, alterarTexto: function(){
            this.$emit('alterouTexto',{
                titulo: this.titulo,
                caixa: this.caixaSel
            })
        }
    }
}
</script>

<style>
    #ferramentas{
        width: 200px;
        height: 120px;
        border: 1px solid #fff;
        margin: 30px auto 10px auto;
        border: 1px solid black;
        background: lightgray;

    }
    #ferramentas select{
        width: 200px;
        border: none;
        margin-bottom: 20px;
        background: lightgray;
    }
    #paleta{
        width: 200px;
        height: 130px;
        display: flex;
        margin: 0 5px 0 5px;
    }
    .cor{
        width: 60px;
        height: 60px;
        border: 1px solid #fff ;
        margin-right: 3px;
    }

    .nomeCaixa{
        display: flex;
    }
    .nomeCaixa input{
        width: 163px;
    }
</style>