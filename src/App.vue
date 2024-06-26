<script setup>
import { reactive, ref } from 'vue'
const titulo = ref('oi vuejs')
const mostrarresultado = ref(false)
const categorias = [{
  id: 1,
  nome: 'eletronicos'
},
{
  id: 2,
  nome: 'vestuario'

},]
const produto = reactive({
  nome: '',
  preco: 0,
  quantidade: 0,
  categoria: [],
})

</script>


<template>
  <h1>{{ titulo }}</h1>
  <button class="btn btn-primary" @click="mostrarresultado = !mostrarresultado">resultado</button>
  <div class="container">
    <div v-if="!mostrarresultado" class="formulario">
      <h2> formulario </h2>
      <input type="text" v-model="titulo">
      <div class="row">
        <label for="nome">Nome</label>
        <input type="text" v-model="produto.nome">
      </div>





      <div class="row">
        <label for="nome">Email</label>
        <input type="text" v-model="produto.email" >
      </div>


      <div class="row">
        <label for="nome">senha</label>
        <input type="text" v-model="produto.senha">
      </div>


      <div class="row">
        <label for="nome">confirme a senha </label>
        <input type="text" v-model="produto.confirmaçãosenha">
      </div>

      <div class="row">
        <label for="nome">data de nascimento</label>
        <input type="text" v-model="produto.data" >
      </div>


      <div class="row">
        <label for="quantidade">endereço</label>
        <input type="text" v-model="produto.endereço" >
      </div>
      
      <div class="row">
        <label for="quantidade">cidade</label>
        <input type="text" v-model="produto.cidade" >
      </div>

<select>
  
  <label for="estado">estado</label>
  <input type="option" v-model="produto.estado">
  <option value="estado">AC</option>
  <option value="estado">AL</option>
  <option value="estado">AP</option>
  <option value="estado">AM</option>
  <option value="estado">BA</option>
  <option value="estado">CE</option>
  <option value="estado">DF</option>
  <option value="estado">ES</option>
  <option value="estado">GO</option>
  <option value="estado">MA</option>
  <option value="estado">MT</option>
  <option value="estado">MS</option>
  <option value="estado">MG</option>
  <option value="estado">PA</option>
  <option value="estado">PB</option>
  <option value="estado">PR</option>
  <option value="estado">PE</option>
  <option value="estado">PI</option>
  <option value="estado">RJ</option>
  <option value="estado">RN</option>
  <option value="estado">RS</option>
  <option value="estado">RO</option>
  <option value="estado">RR</option>
  <option value="estado">SC</option>
  <option value="estado">SP</option>
  <option value="estado">SE</option>
  <option value="estado">TO</option>
</select>


     <fieldset>
        <legend>linguagem de programação</legend>
        <div class="items-checkbox">
          <input type="checkbox" value="pyton" v-model="produto.categoria" /> pyton
          <input type="checkbox" value="java" v-model="produto.categoria" /> java 
          <input type="checkbox" value="php" v-model="produto.categoria" /> php
        </div>
      </fieldset>



      
    </div>
    <div v-if="mostrarresultado" class="resultado">
      <h2>Dados do produto</h2>
      <p> estado: {{ produto.estado }}</p>
      <p>email:{{ produto.email }}</p>
      <p>Nome:{{ produto.nome }}</p>
      <p>quantidade:{{ (produto.quantidade) }}</p>
      <p>categoria:{{ produto.categoria }}</p>
      <p>{{ mostrarresultado }}</p>
    </div>

  </div>
</template>


<style scoped>
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 2rem;
  margin-top: 1rem;
}

.formulario,
.resultado {
  width: 45vw;
  min-height: 70vh;
  padding: 20px;
  border-radius: 20px;

}

.formulario {
  background-color: rgb(255, 167, 167);

}

.resultado {
  background-color: rgb(198, 137, 255);
}

.formulario .row {
  width: 80%;
  margin: 1.3rem 0;
  display: grid;
  justify-content: 1fr 3fr;
}

.formulario .items-checkbox {
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: center;
}

fieldset {
  border-image-repeat: 10px;
  background-color: rgb(255, 255, 255);
}
</style>