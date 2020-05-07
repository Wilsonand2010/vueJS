<template>
    <div>
        <button v-on:click="show = !show" class="btn btn-primary" type="submit">Editar</button>
        <transition>
            <div v-if="show" class="form-todo form-group">
                <p>
                    <input v-model="titulo" placeholder="Insira o Título" type="text" name="titulo" 
                    class = "form-control" />
                </p>
                <p>
                <textarea v-model="descricao" placeholder="Insira a Descrição" name ="descricao"
                    class="form-control"></textarea>
                </p>
                <button v-on:click="editarCadastro(cadastros)" class="btn btn-primary" type="submit">Re-Cadastrar</button>
            </div>
         </transition>
    </div>
</template>

<script>
export default {

    props:['cadastros','show'],

    data(){
            
        return{
        titulo: '',
        descricao: '',
        marcado: ''
        }
    },


    methods:{

        editarCadastro(cadastros){
            
            if( this.titulo === '' || this.descricao === ''){
                return;
            }

            cadastros.titulo=this.titulo
            cadastros.descricao=this.descricao
        

            this.titulo = '',
            this.descricao = ''          
            console.log(cadastros);

        }
    }
}
</script>