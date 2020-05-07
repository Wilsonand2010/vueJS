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

      <Editar
      v-bind:cadastros="cadastro"
      v-bind:key="cadastro.id"
      v-on:editCadastro="editar"
      ></Editar>

      <Marcar 
      v-bind:show="show"
      v-bind:cadastros="cadastro"
      v-bind:key="cadastro.id"
      v-on:marcarCadastro="marcar">
      </Marcar>
    </div>
  </div>
<hr />
</div>
</template>

<script>

import Adicionar from './components/Adicionar';
import Marcar from './components/Marcar';
import Editar from './components/Editar'


export default {
  name: 'App',
  components: {
    Adicionar,
    Marcar,
    Editar
  },

  data(){
    return{
      show: true,
      cadastros: [],
      titulo: '', 
      descricao:'', 
      marcado: false
    }
  },

  methods:{
    
      adicionar(cadastro){
          // Chama component Adicionar
          this.cadastros.push(cadastro)
      },

      removerCadastro(index){
          this.cadastros.splice(index, 1);
          
      },

      editar(){
      // Chama o componente Editar
      },

      marcar(){
      // Chama o componente Marcar        
      }

  }
}
</script>
<style>
</style>