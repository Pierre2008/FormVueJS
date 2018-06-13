<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Identifiez-vous</h2>
    <form method="post" action="#" id="form">
      <label for="nom">Nom</label>
      <input type="text" id="nom" name="Nom">

      <label for="prenom">Prénom</label>
      <input type="text" id="prenom" name="Prenom">

      <label for="mail">Email</label>
      <input type="email" id="mail" name="Mail">

      <label for="password">Mot de passe</label>
      <input type="password" id="password" name="Password">

      <input type="button" value="Envoyer" v-on:click="toLocalStorage()">
    </form>
  </div>
</template>

<script>
export default {
  name: 'Form',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
      toLocalStorage: function () {
          storData();
      }
  }
}

function formData() {
    let form = document.getElementById('form');
    let formData = [];

    for (let i = 0; i < form.length; i++) {
        formData[form[i].name] = form[i].value;
    }
    return formData
}

function storData() {
    let formulaireData = formData();

    for (let key in formulaireData) {
        localStorage.setItem(key, formulaireData[key])
    }
}






</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
  width: 300px;
  margin: auto;
}

input {
  height: 25px;
  width: 100%;
  margin-bottom: 20px;
  }

  input[type=button] {
    width: 50%;
    background-color: #2c3e50;
    color: white;
  }

</style>
