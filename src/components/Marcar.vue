<template>
    <div class="form-group">
            <div class="form-check">
            <input v-on:click="marcarCadastro(cadastro)" class="form-check-input" type="checkbox" id="gridCheck">
                <label class="form-check-label" for="gridCheck">
                    Marcar como Feito
                </label>
            </div>
        </div>  
</template>

<script>
export default {


    props:['cadastro'],

    data(){
        return{
            cadastros: this.cadastro,
        }
    },


    methods:{
        marcarCadastro(cadastros){

            if(cadastros.marcado === false)
                cadastros.marcado = true;
            else
                cadastros.marcado = false

        console.log(cadastros.marcado);              
      
        },
    }
}
</script>