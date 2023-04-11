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
</script>

<template>
  <div class="container">
    <div>
      <input type="text" v-model="name" placeholder="Nome" minlength="2" maxlength="40 " />
    </div>
    <div>
      <input type="email" v-model="email" placeholder="Email" />
    </div>
    <div>
      <input type="password" v-model="password" placeholder="Senha" />
    </div>
    <div>
      <input type="password" v-model="confirmPassword" placeholder="Confirmar senha" />
    </div>
    <div>
      <input type="text" v-model="address" placeholder="Endereço" />
    </div>
    <div>
      <input v-model="city" placeholder="Cidade" />
    </div>
    <div class="box1">
    <div>
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
    <div>
      <p>Data de nascimento:</p>
      <input type="date" v-model="date" min="1920-01-01" max="2023-04-14"/>  
    </div>
    <div>
      <p>Gênero:</p>
    </div>
    <div>
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
  </div>
</template>

<style scoped>
.container{
  padding: 15%;
  background-color: royalblue;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 40px 50px 40px 50px;
}
.box1{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
</style>
