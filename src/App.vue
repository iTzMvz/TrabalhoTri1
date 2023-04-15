<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmaSenha = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const data = ref('')
const genero = ref('')
const bio = ref('')
const hobbies = ref('')
const linguagemProgramacao = ref([])
const mensagem = ref('')
const enviar = ref(false)


function confirmar() {
  if (senha.value != confirmaSenha.value) {
    mensagem.value = 'A senha está incorreta'
  } else {
  return enviar.value = !enviar.value
  }
}
</script>

<template>
  <div class="container">
    <form @submit.prevent = 'enviar = confirmar()'>
    <div class="login">
      <h1>Insira Suas Informações</h1>
      <div class="input-field">
        <label>Nome</label>
        <input type="text" v-model="nome"  placeholder="Nome" minlength="1" maxlength="40 " required  />
      </div>
      <div class="input-field">
        <label>Email</label>
        <input type="email" v-model="email" minlength="1" placeholder="Email" required  />
      </div>
      <div class="input-field">
        <label>Senha:</label>
        <input type="password" v-model="senha" minlength="1" maxlength="20" placeholder="Senha" required />
      </div>
      <div class="input-field">
        <label>Confirme a Senha:</label>
        <input type="password" v-model="confirmaSenha" minlength="1" maxlength="20" placeholder="Confirmar senha" required  />
      </div>
      <div class="input-field">
        <label>Endereço:</label>
        <input type="text" v-model="endereco" minlength="1" placeholder="Endereço" required  />
      </div>
      <div class="input-field">
        <label>Cidade:</label>
        <input type="text" v-model="cidade" minlength="1" placeholder="Cidade" required  />
      </div>
      <div class="input-field">
        <label>Estado</label>
        <select style="margin-top: 0" v-model="estado" required >
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
        <input type="date" v-model="data" min="1920-01-01" max="2023-04-14" required  />
      </div>
      <div class="input-field">
        <label>Gênero:</label>
        <div class="input-radio">
          <div class="radio-item">
            <input type="radio" v-model="genero" value="Masculino" /><span>Masculino</span>
          </div>
          <div class="radio-item">
            <input type="radio" v-model="genero" value="Feminino" /><span>Feminino</span>
          </div>
          <div class="radio-item">
            <input type="radio" v-model="genero" value="Outro" /><span>Outro</span>
          </div>
        </div>
      </div>
      <div class="input-field">
        <label for="linguagemprogram">Linguagem de programação:</label>
        <p>
          <input type="checkbox" v-model="linguagemProgramacao" value="Java" />Java
        </p>
        <p>
          <input type="checkbox" v-model="linguagemProgramacao" value="Python" />Python
        </p>
        <p>
          <input type="checkbox" v-model="linguagemProgramacao" value="JavaScript" />JavaScript
        </p>
        <p>
          <input type="checkbox" v-model="linguagemProgramacao" value="C#">C#
        </p>
        <p>
          <input type="checkbox" v-model="linguagemProgramacao" value="C++">C++
        </p>
        <p>
          <input type="checkbox" v-model="linguagemProgramacao" value="Outro">Outro
        </p>
      </div>
      <div class="input-field">
        <label>Hobbies:</label>
        <input type="text" v-model="hobbies" minlength="1" placeholder="Hobbies" required >
      </div>
      <div class="input-field">
        <label>Biografia:</label>
        <textarea v-model="bio" minlength="1" maxlength="200" placeholder="Biografia" required ></textarea>
      </div>
      <button type="submit" value="confirm">Enviar</button>
      <p style="color: red;">{{ mensagem }}</p>
    </div>
  </form>
    <div class="info">
      <div v-if="enviar">
        <h1>Suas Informações</h1>
        <p class="box">Nome: {{ nome }}</p>
        <p class="box">Email: {{ email }}</p>
        <p class="box">Senha: {{ senha }}</p>
        <p class="box">Data de nascimento: {{ data }}</p>
        <p class="box">Estado: {{ estado }}</p>
        <p class="box">Cidade: {{ cidade }}</p>
        <p class="box">Endereço: {{ endereco }}</p>
        <p class="box">Gênero: {{ genero }}</p>
        <p class="box">Hobbie: {{ hobbies }}</p>
        <p class="box">Linguagem de Programação: {{ linguagemProgramacao.join(", ") }}</p>
        <p class="box" style="width: 332px;">Biografia: {{ bio }}</p>
      </div>
    </div>
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
  background-color: #C7D1D9;
}
button:hover{
  transition: 0.9s;
  background-color: #1A2126;
  color: white;
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