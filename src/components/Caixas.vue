<template>
  <div id="caixa">
      <div class="caixinhas" v-for="(caixa, index) in caixinhas" :key="index" :style="caixa.cor">
          {{caixa.titulo}}
      </div>
  </div>
</template>

<script>
export default {
    name: "Caixas",
    props: ['caixinhas']
}
</script>

<style>
    #caixa{
        width: 200px;
        height: 120px;
        border: 1px solid black;
        margin: 30px auto 10px auto;
        display: flex;
        flex-wrap: wrap;
        background:lightgrey;
    }
    .caixinhas{
        width: 50px;
        height: 50px;
        border: 1px solid black;
        margin: 30px 5px 0 5px;
        text-align: center;
        user-select: none;
        display: flex;
    }
</style>