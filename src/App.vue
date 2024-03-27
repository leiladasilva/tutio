
<script setup>
import {reactive, ref} from 'vue'
const titulo = ref ('oi vuejs')
const mostrarresultado = ref(false)
const produto = reactive({
    nome:'',
    preco:0,
    quantidade:0,
    categoria:[],
})
</script>


<template>
    <h1>{{ titulo }}</h1>
    <div class="container">
        <div class="formulario">
            <h2>  formulario  </h2>
            <input type="text" v-model="titulo">
            <div class="row">
                <label for="nome">Nome</label>
                <input type="text" v-model="produto.nome">
            </div>

            <div class="row">
                <label for="preco">preço</label>
                <input type="text">
            </div>

            <div class="row">
                <label for="quantidade">quantidade</label>
                <input type="text">
            </div>

<button @click="mostrarresultado= !mostrarresultado" >mostrar</button>

        </div>
        <div class="resultado">
            <h2>Dados do produto</h2>
            <p>Nome:{{ produto.nome }}</p>
            <p>preço:{{ produto.preco }}</p>
            <p>quantidade:{{ produto.quantidade }}</p>
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
</style>