<script setup>
import {reactive, ref} from 'vue'
const titulo = ref ('oi vuejs')
const mostrarresultado = ref(false)
const categorias = [{
    id: 1,
    nome: 'eletronicos'
},
{
    id:2,
    nome:'vestuario'

},]
const produto = reactive({
    nome:'',
    preco:0,
    quantidade:0,
    categoria:[],
})
function formartarpreco(preco){
    return  `R$ ${preco.toFixed(2).replace('.','.')}`
}
</script>


<template>
    <h1>{{ titulo }}</h1>
    <button @click="mostrarresultado= !mostrarresultado" >mostrar</button>
    <div class="container">
        <div class="formulario">
            <div v-if="!mostrarresultado" class="formulario">
            <h2>  formulario  </h2>
            <input type="text" v-model="titulo">
            <div class="row">
                <label for="nome">Nome</label>
                <input type="text" v-model="produto.nome">
            </div>

            <div class="row">
                <label for="preco">preço</label>
                <input type="number" step="0.01" v-model="produto.preco">
            </div>

            <div class="row">
                <label for="quantidade">quantidade</label>
                <input type="number" v-model="produto.quantidade">
            </div>
            <fieldset>
                <legend>categoria</legend>
                <div class="items-checkbox">
                <input type="checkbox"  value="categoria 1" v-model="produto.categoria"/> categoria 1
                <input type="checkbox"  value="categoria 2" v-model="produto.categoria"/> categoria 2
                <input type="checkbox"  value="categoria 3" v-model="produto.categoria"/> categoria 3 
            </div>
            </fieldset>
</div>


        </div>
        <div v-if="mostrarresultado" class="resultado">
            <h2>Dados do produto</h2>
            <p>Nome:{{ produto.nome }}</p>
            <p>preço:{{ formartarpreco(produto.preco) }}</p>
            <p>quantidade:{{ (produto.quantidade) }}</p>
            <p>categoria:{{ produto.categoria }}</p>
            <p>{{ mostrarresultado }}</p>
        </div>
      
    </div>
</template>


<style scoped>
.container{
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 2rem;
    margin-top: 1rem;
}
.formulario, .resultado{
width: 45vw;
min-height: 70vh;
padding: 20px;
border-radius: 20px;

}
.formulario{
    background-color: rgb(255, 167, 167);
    
    }
.resultado{
    background-color: rgb(198, 137, 255);
}
.formulario .row{
    width: 80%;
    margin: 1.3rem 0;
    display: grid;
    justify-content:1fr 3fr ;
}
.formulario .items-checkbox{
display: grid;
grid-template-columns: auto 1fr ;
align-items: center;
}
fieldset{
    border-image-repeat: 10px;
    background-color: aqua;
}
</style>