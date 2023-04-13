<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const password = ref('')
const confirmPassword = ref('')
const address = ref('')
const city = ref('')
const state = ref('')
const date = ref('')
const sex = ref('')

const send = ref(false)
function confirm() {
  if (password.value != confirmPassword.value) {
    alert("senha incorreta")
  }
  else {
    send.value = !send.value
  }
}
</script>

<template>
  <div class="container">
    <h1>Insira Suas Informações</h1>
    <div class="box">
      <input type="text" v-model="name" placeholder="Nome" minlength="2" maxlength="40 " />
    </div>
    <div class="box">
      <input type="email" v-model="email" placeholder="Email" />
    </div>
    <div class="box">
      <input type="password" v-model="password" placeholder="Senha" />
    </div>
    <div class="box">
      <input type="password" v-model="confirmPassword" placeholder="Confirmar senha" />
    </div>
    <div class="box">
      <input type="text" v-model="address" placeholder="Endereço" />
    </div>
    <div class="box">
      <input v-model="city" placeholder="Cidade" />
    </div>
    <div >
    <div class="box" >
      <select v-model="state">
        <option value="">Estado</option>
        <option value="AC">Acre</option>
        <option value="AL">Alagoas</option>
        <option value="AP">Amapá</option>
        <option value="AM">Amazonas</option>
        <option value="BA">Bahia</option>
        <option value="CE">Ceará</option>
        <option value="DF">Distríto Federal</option>
        <option value="ES">Espírito Santo</option>
        <option value="GO">Goiás</option>
        <option value="MA">Maranhão</option>
        <option value="MT">Mato Grosso</option>
        <option value="MS">Mato Grosso do Sul</option>
        <option value="MG">Minas Gerais</option>
        <option value="PA">Pará</option>
        <option value="PB">Paraíba</option>
        <option value="PE">Pernambuco</option>
        <option value="PI">Píaui</option>
        <option value="PR">Paraná</option>
        <option value="RJ">Rio de Janeiro</option>
        <option value="RN">Rio Grande do Norte</option>
        <option value="RS">Rio Grande do Sul</option>
        <option value="RO">Rondônia</option>
        <option value="RR">Roraima</option>
        <option value="SC">Santa Catarina</option>
        <option value="SP">São Paulo</option>
        <option value="SE">Sergipe</option>
        <option value="TO">Tocantins</option>
      </select>
      
    </div>
    <div class="box">
      <p>Data de nascimento:</p>
      <input type="date" v-model="date" min="1920-01-01" max="2023-04-14"/>  
    </div>
    <div>
      <p>Gênero:</p>
    </div>
    <div class="box">
      <div>
      <input type="radio" v-model="sex" value="male" />Masculino
    </div>
    <div>
      <input type="radio" v-model="sex" value="female" />Feminino
    </div>
    <div>
      <input type="radio" v-model="sex" value="other" />Outro
    </div>
    </div>
  </div>
  <button type="button" @click="confirm ">enviar</button>
</div>
<div v-if="send">
      <h1>Suas Informações</h1>
      <p class="text-danger">Nome: </p>
      <p>{{ nome }}</p>
      <p class="text-danger">Email: </p>
      <p>{{ email }}</p>
      <p class="text-danger">Senha: </p>
      <p>{{ senha }}</p>
      <p class="text-danger">Data de nascimento: </p>
      <p>{{ nascimento }}</p>
      <p class="text-danger">Estado: </p>
      <p>{{ estado }}</p>
      <p class="text-danger">Hobbie: </p>
      <p>{{ hobbie }}</p>
      <p class="text-danger">Linguagem de Programação: </p>
      {{ linguagemProg }}
      <p class="text-danger">Biografia: </p>
      <p class="text-bio">{{ bio }}</p>
</div>
</template>

<style scoped>
.container{
  background-color: royalblue;
  display: flex;
  flex-direction: column;
  align-items:center;
  padding: 40px 0 40px 0;
}
.box{
margin: 5px;
}
input{
  border-radius: 6px;
  padding: 5px;
}
select{
  border-radius: 6px;
  padding: 5px;   
}
</style>
