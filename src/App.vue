<template>
  <div id="app">
  <hr />
    <h1>Sistema de Cadastro</h1>
    <Adicionar v-on:addCadastro="adicionar"></Adicionar>
        <div class="list-group">
        <div class="list-group-item" v-for="(cadastro, index) in cadastros" v-bind:key="cadastro.id">
            <p>Titulo: {{ cadastro.titulo }} </p>
            <p>Descrição: {{ cadastro.descricao }} </p>
            
            <button v-on:click="removerCadastro(index)" class="btn btn-primary" type="submit">Excluir</button>
            
            <button v-on:click="editarCadastro(cadastro)" class="btn btn-primary" type="submit">Editar</button>
            
            <Marcar 
              v-bind:cadastro="cadastro"
              v-bind:key="cadastro.id"
              v-on:marcarCadastro="marcar"></Marcar>
        </div>
      </div>
  <hr />
  </div>
</template>

<script>

import Adicionar from './components/Adicionar';
import Marcar from './components/Marcar'

export default {
  name: 'App',
  components: {
    Adicionar,
    Marcar
  },

  data(){
    return{
      cadastros: [],
      titulo: '', 
      descricao:'', 
      marcado: false
    }
  },

  methods:{
    
      adicionar(cadastro){
          
          this.cadastros.push(cadastro)
      },

      removerCadastro(index){
          this.cadastros.splice(index, 1);
          
      },

      editarCadastro(cadastro){
        console.log(cadastro);
        cadastro.titulo = '1'
      },

      marcar(){
      // Chama o componente Marcar        
      }

  }
}
</script>
<style>
</style>