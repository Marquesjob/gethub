<script>
import Nav from './components/Nav.vue'
import Card from './components/Card.vue'

export default {
  components: {
    Nav,
    Card
  },

  props: { }
  
}

</script>

<template>

  <div class="container">
    <Nav/>
    <div class="subtitle">
      <p>Liste os <strong class="subtitle__strong">repositórios</strong> e obtenha informações do seu perfil <strong class="subtitle__strong">Git</strong> favorito através do <strong class="subtitle__strong">GET</strong>hub ;)</p>
    </div>
    <Card />
    <Card />
  </div>

</template>

<style>
@import './assets/base.css';

  .container {
    margin: 0 auto;
    max-width: 1200px;
  }

  .subtitle {
    margin: 0 auto;
    display: flex;
    justify-content: center;
    font-family: 'poppins', sans-serif;
    color: var(--fifth-dark);
    font-weight: 300;
    font-size: 17px;
  }

  .subtitle__strong {
    color: var(--third-dark);
  }

  p {
    margin-top: 0;
  }

  

</style>
