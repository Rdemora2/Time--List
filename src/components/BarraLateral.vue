<template>
   <header>
    <h1>
        <p>Time List</p>
        <hr>
        <img src="../assets/logo.png" alt="logo do vue">
    </h1>
    <button class="button is-small is-rounded is-focused" @click="alterarTema">
      {{ textoBotao }}
    </button>
   </header> 
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BarraLateral',
    emits: ['aoTemaAlterado'],
    data () {
      return {
        modoEscuroAtivo: false
      }
    },
    computed:{
      textoBotao () {
        if (this.modoEscuroAtivo) {
          return 'Enable Light Mode'
        }
        return 'Enable Dark Mode'
      }
    },
    methods: {
      alterarTema () {
        this.modoEscuroAtivo = !this.modoEscuroAtivo
        this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
      }
    },
})
</script>

<style scoped>
header p{
  color: #fff;
  font-size: 1.6rem;
  margin-bottom: 10px;
}
header hr{
  border: 1px solid #9ec1e1;
}
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
  header button{
    width: 50%;
    height: 40px;
    font-size: 0.88rem;
    border: none;
  }
  header p{
  font-size: 2.6rem;
  }
  header hr{
  width: 85vw;
  }
}
</style>