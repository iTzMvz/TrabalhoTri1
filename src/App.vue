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
const bio = ref('')
const hobbies = ref('')
const programLanguage = ref([])
const send = ref(false)
const contador = ref(0)

function confirm() {
  if (password.value != confirmPassword.value) {
    alert('senha incorreta')  
  } else {
    send.value = !send.value
    return console.log(contador.value++)
  }
}
</script>

<template>
  <div class="container">
    <form @submit.prevent = 'send = confirm()'>
    <div class="login">
      <h1>Insira Suas Informações</h1>
      <div class="input-field">
        <label>Nome</label>
        <input type="text" v-model="name"  placeholder="Nome" minlength="1" maxlength="40 " />
      </div>
      <div class="input-field">
        <label>Email</label>
        <input type="email" v-model="email" minlength="1" placeholder="Email" />
      </div>
      <div class="input-field">
        <label>Senha:</label>
        <input type="password" v-model="password" minlength="1" maxlength="20" placeholder="Senha" />
      </div>
      <div class="input-field">
        <label>Confirme a Senha:</label>
        <input type="password" v-model="confirmPassword" minlength="1" maxlength="20" placeholder="Confirmar senha" />
      </div>
      <div class="input-field">
        <label>Endereço:</label>
        <input type="text" v-model="address" minlength="1" placeholder="Endereço" />
      </div>
      <div class="input-field">
        <label>Cidade:</label>
        <input type="text" v-model="city" minlength="1" placeholder="Cidade" />
      </div>
      <div class="input-field">
        <label>Estado</label>
        <select style="margin-top: 0" v-model="state">
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
      <div class="input-field">
        <label>Data de nascimento:</label>
        <input type="date" v-model="date" min="1920-01-01" max="2023-04-14" />
      </div>
      <div class="input-field">
        <label>Gênero:</label>
        <div class="input-radio">
          <div class="radio-item">
            <input type="radio" v-model="sex" value="Masculino" /><span>Masculino</span>
          </div>
          <div class="radio-item">
            <input type="radio" v-model="sex" value="Feminino" /><span>Feminino</span>
          </div>
          <div class="radio-item">
            <input type="radio" v-model="sex" value="Outro" /><span>Outro</span>
          </div>
        </div>
      </div>
      <div class="input-field">
        <label for="linguagemprogram">Linguagem de programação:</label>
        <p>
          <input type="checkbox" v-model="programLanguage" value="Java" />Java
        </p>
        <p>
          <input type="checkbox" v-model="programLanguage" value="Python" />Python
        </p>
        <p>
          <input type="checkbox" v-model="programLanguage" value="JavaScript" />JavaScript
        </p>
        <p>
          <input type="checkbox" v-model="programLanguage" value="C#">C#
        </p>
        <p>
          <input type="checkbox" v-model="programLanguage" value="C++">C++
        </p>
        <p>
          <input type="checkbox" v-model="programLanguage" value="Outro">Outro
        </p>
      </div>
      <div class="input-field">
        <label>Hobbies:</label>
        <input type="text" v-model="hobbies" minlength="1" placeholder="Hobbies">
      </div>
      <div class="input-field">
        <label>Biografia:</label>
        <textarea v-model="bio" minlength="1" maxlength="200" placeholder="Biografia"></textarea>
      </div>
      <input type="submit" @click="confirm">
    </div>
    <div class="info">
      <div v-if="send" >
        <h1>Suas Informações</h1>
        <p class="box">Nome: {{ name }}</p>
        <p class="box">Email: {{ email }}</p>
        <p class="box">Senha: {{ password }}</p>
        <p class="box">Data de nascimento: {{ date }}</p>
        <p class="box">Estado: {{ state }}</p>
        <p class="box">Cidade: {{ city }}</p>
        <p class="box">Endereço: {{ address }}</p>
        <p class="box">Gênero: {{ sex }}</p>
        <p class="box">Hobbie: {{ hobbies }}</p>
        <p class="box">Linguagem de Programação: {{ programLanguage.join(", ") }}</p>
        <p class="box">Biografia: {{ bio }}</p>
      </div>
    </div>
  </form>
  </div>
</template>

<style scoped>

input {
  border-radius: 6px;
  padding: 5px;
  margin-top: 10px;
  background-color: #C7D1D9;
  box-shadow: 4px 7px 7px #1A2126;
}

select {
  border-radius: 6px;
  padding: 5px;
  margin-top: 10px;
  background-color: #C7D1D9;
  box-shadow: 4px 7px 7px #1A2126;  
}

button {
  margin: 5px 5px 20px 5px;
  padding: 5px 10px 5px 10px;
  border-radius: 3px;
}
textarea{
  background-color: #C7D1D9;
  box-shadow: 4px 7px 7px #1A2126;  
  border-radius: 6px;
  margin-bottom: 20px;
}
.container {
  background-color: #434F59;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 40px 0 40px 0;
  border-radius: 12px;
  width: 450px;
  margin: 50px auto;
}

.box {
  margin: 0 0 5px 0;
}

.login {
  display: flex;
  flex-direction: column;
}

.input-field {
  display: flex;
  flex-direction: column;
  margin-top: 8px;
}

.input-field input:not(:first-child) {
  margin-top: 0;
}

.input-field .input-radio {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.input-field .input-radio input[type='radio'] {
  display: inline;
  margin-right: 10px;
}

.input-field .input-radio span {
  margin-right: 30px;
}

.info{
  word-wrap: break-word;
  line-break: anywhere;
}

</style>