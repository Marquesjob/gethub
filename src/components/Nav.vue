<script>
import Github from '@/components/icons/Github.vue';
import axios from "axios"
import Card from './Card.vue';

export default {

  data() {
    return {
      infos: [],
      username: null
    }
  },

  methods: {
    filter(user = string) {        
        user = (`https://api.github.com/users/${user}/repos`)
        user = user.toLowerCase();
        return user;   
    },
    getUser(user) {
      if ( user === null) {
          window.alert('Você precisa preencher o campo pra eu buscar o repositório, engraçadinho  (    ͡° ͜ʖ ͡°)')
          return;
      } else {
         axios
        .get(this.filter(user))
        .then(response => (this.infos = response.data))
        this.username = null;
      }
    }
  },

  components: { Github, Card }
}

</script>

<template>

  <div class="nav">
    <div class="nav__label">
      <Github class="nav__label__icon" />
      <strong> GET</strong>hub.
    </div>  
      <input v-model="username" class="nav__input" placeholder="Digite aqui o nome do perfil" required>
      <button @click="getUser(username)" v-on:keyup.enter="getUser(username)" class="nav__button">Buscar</button> 
  </div>
  <div class="subtitle">
    <p>Liste os <strong class="subtitle__strong">repositórios </strong> do seu perfil <strong
        class="subtitle__strong">Git</strong> favorito,<br/> obtenha informações sobre commits, datas e mais, através do <strong class="subtitle__strong">GET</strong>hub ;)
    </p>
  </div>

  <Card v-for="info in infos" :repoData="info" />

</template>

<style>
.nav {
  margin: 0 auto;
  margin-top: 10px;
  height: 8em;
  max-width: 1100px;
  display: flex;
  justify-content: center;
  align-items: center;
  /* border-bottom: 1px solid;
    border-color: var(--third-dark); */
}

.nav__label {
  font-family: 'poppins', sans-serif;
  font-weight: bold;
  font-size: 30px;
  color: var(--fifth-dark);
}

.nav__label__strong {
  color: var(--third-dark);
}
.nav__form {
  display: contents;
}

.nav__input {
  box-sizing: border-box;
  padding-left: 20px;
  width: 50%;
  height: 35px;
  margin-left: 30px;
  border: none;
  background-color: var(--second-dark);
  font-family: 'poppins', sans-serif;
  color: var(--fifth-dark);
}

.nav__input::placeholder {
  font-family: 'poppins', sans-serif;
  color: #90a0d94f;
}

.nav__input:focus {
  outline: 0;
}

.nav__button {
  padding: 0;
  width: 100px;
  height: 35px;
  border: none;
  background-color: var(--second-dark);
  font-family: 'poppins', sans-serif;
  font-weight: bold;
  font-size: 15px;
  color: var(--third-dark);
  cursor: pointer;
  background: linear-gradient(90deg, var(--second-dark) 50%, var(--first-dark) 0) var(--_p, 100%)/200% no-repeat;
  transition: .2s;
}

.nav__button:hover {
  --_p: 0%;
}

.subtitle {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  font-family: 'poppins', sans-serif;
  color: var(--fifth-dark);
  font-weight: 300;
  font-size: 17px;
  text-align: center;
}

.subtitle__strong {
  color: var(--third-dark);
}

p {
  margin-top: 0;
}
</style>
