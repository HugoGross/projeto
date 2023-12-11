<script setup>

</script>

<template>
<form>
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome" required>

  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required>

  <label for="password">Senha:</label>
  <input type="password" id="password" name="password" required>

  <label for="confirm-password">Confirmação de senha:</label>
  <input type="password" id="confirm-password" name="confirm-password" required>

  <label for="dataNascimento">Data de nascimento:</label>
  <input type="date" id="dataNascimento" name="dataNascimento" required>

  <label for="endereco">Endereço:</label>
  <input type="text" id="endereco" name="endereco" required>

  <label for="cidade">Cidade:</label>
  <input type="text" id="cidade" name="cidade" required>

  <label for="estado">Estado:</label>
  <select id="estado" name="estado" required>
    <option value="" selected disabled>Selecione o estado</option>
    <option value="AC">Acre</option>
    <option value="AL">Alagoas</option>
    <option value="AP">Amapá</option>
    <option value="AM">Amazonas</option>
    <option value="BA">Bahia</option>
    <option value="CE">Ceará</option>
    <option value="DF">Distrito Federal</option>
    <option value="ES">Espírito Santo</option>
    <option value="GO">Goiás</option>
    <option value="MA">Maranhão</option>
    <option value="MT">Mato Grosso</option>
    <option value="MS">Mato Grosso do Sul</option>
    <option value="MG">Minas Gerais</option>
    <option value="PA">Pará</option>
    <option value="PB">Paraíba</option>
    <option value="PR">Paraná</option>
    <option value="PE">Pernambuco</option>
    <option value="PI">Piauí</option>
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
  
  <label for="hobbies">Hobbies:</label>
  <input type="text" id="hobbies" name="hobbies">

  <label for="linguagens">Linguagens de programação:</label>
  <input type="text" id="linguagens" name="linguagens">

  <label for="biografia">Biografia:</label>
  <textarea name="biografia" id="biografia" cols="30" rows="10"></textarea>
  <form @submit.prevent="submitForm">
      <button type="submit">Salvar</button>
    </form>
 </form>
 <div>
  
    <div v-if="showUserData">
      <h2>Dados do usuário:</h2>
      <p>Nome: {{ userData.nome }}</p>
      <p>E-mail: {{ userData.email }}</p>
      <p>Data de nascimento: {{ userData.dataNascimento }}</p>
      <p>Endereço: {{ userData.endereco }}, {{ userData.cidade }}, {{ userData.estado }}</p>
      <p>Hobbies: {{ userData.hobbies }}</p>
      <p>Linguagens de programação: {{ userData.linguagens }}</p>
      <p>Biografia: {{ userData.biografia }}</p>
    </div>
  </div>
</template>
		
  <script>
export default {
  data() {
    return {
      userData: {},
      showUserData: false,
    };
  },
  methods: {
    submitForm() {
      
      const nome = document.getElementById("nome").value;
      const email = document.getElementById("email").value;
      const dataNascimento = document.getElementById("dataNascimento").value;
      const endereco = document.getElementById("endereco").value;
      const cidade = document.getElementById("cidade").value;
      const estado = document.getElementById("estado").value;
      const hobbies = document.getElementById("hobbies").value;
      const linguagens = document.getElementById("linguagens").value;
      const biografia = document.getElementById("biografia").value;

      
      this.userData = {
        nome,
        email,
        dataNascimento,
        endereco,
        cidade,
        estado,
        hobbies,
        linguagens,
        biografia,
      };

      this.showUserData = true;
    },
  },
};
</script>


<style scoped>
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
}
div {
  max-width: 600px;
  max-height: 285px;
  margin: 0 auto;
  background-color: #fffdfd;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0px 0px 10px rgba(0, 119, 255, 0.2);
}
form {
  max-width: 600px;
  margin: 0 auto;
  background-color: #fffdfd;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0px 0px 10px rgba(0, 119, 255, 0.2);
}

label {
  display: block;
  margin-bottom: 10px;
  font-weight: bold;
}

input[type="text"],
input[type="email"],
input[type="password"],
input[type="date"],
select {
  display: block;
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  border: none;
  margin-bottom: 20px;
  box-sizing: border-box;
}

button[type="submit"] {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #45a049;
}

.error {
  color: red;
  margin-bottom: 10px;
}

</style>
