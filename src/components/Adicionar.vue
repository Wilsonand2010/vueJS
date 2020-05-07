<template>
    <div class="form-todo form-group">
        <p>
        <input v-model="titulo" placeholder="Insira o Título" type="text" name="titulo" 
            class = "form-control" />
        </p>
        <p>
            <textarea v-model="descricao" placeholder="Insira a Descrição" name ="descricao"
            class="form-control"></textarea>
        </p>
            <button v-on:click="adicionarCadastro" class="btn btn-primary" type="submit">Cadastrar</button>
    </div>
</template>

<script>

export default {

    data(){
        return{
        titulo: '',
        descricao: '',
        marcado: false
        }
    },


    methods:{
        adicionarCadastro(){
            if( this.titulo === '' || this.descricao === ''){
                return;
            }
            
            this.$emit('addCadastro',{
                titulo: this.titulo,
                descricao: this.descricao,
                marcado: false
            });

            this.titulo = '',
            this.descricao = ''

        }
    }
}
</script>