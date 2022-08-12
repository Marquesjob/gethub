<script>
import Github from '@/components/icons/Github.vue';
import axios from "axios"
import Card from './Card.vue';
import CardForWelcomePage from './CardForWelcomePage.vue'

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
      if (user === null) {
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

  components: { Github, Card, CardForWelcomePage }
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

  <CardForWelcomePage />
  <Card v-for="info in infos" :repoData="info" />

</template>

<style>
.nav {
  margin: 0 auto;
  margin-top: 75px;
  height: 2em;
  max-width: 1100px;
  display: flex;
  justify-content: center;
  align-items: center;
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

@media (max-width: 710px) {
  .nav {
    margin-top: 100px;
    display: block;
    flex-direction: column;
  }
  .nav__label {
    text-align: center;
  }
  .nav__input {
    width: 100%;
    height: 35px;
    padding: 0;
    padding-left: 20px;
    margin: 0;
    margin-top: 10px;
    margin-bottom: 10px;
  }
  .nav__button {
    width: 100%;
    font-size: 17px;
    background: none;
  }
  .card__welcome {
    padding: 0;
  }
  .subtitle {
    font-size: 15px;
  }
  p {
    text-align: center;
    margin-top: 80px;
  }
}

@media (max-width: 576px) {
  .container {
    width: 80%;
  }
  .nav {
    margin-top: 100px;
    display: block;
    flex-direction: column;
  }
  .nav__label {
    text-align: center;
  }
  .nav__input {
    width: 100%;
    height: 35px;
    padding: 0;
    padding-left: 20px;
    margin: 0;
    margin-top: 10px;
    margin-bottom: 10px;
  }
  .nav__button {
    width: 100%;
    font-size: 17px;
    background: none;
  }
  .card__welcome {
    padding: 0;
  }
  .subtitle {
    font-size: 15px;
  }
  p {
    text-align: center;
    margin-top: 80px;
  }
}
</style>
