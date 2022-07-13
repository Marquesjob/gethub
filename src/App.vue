<script>
import Nav from './components/Nav.vue'
  
export default {
  
  components: {
    Nav,
  },
}
</script>

<template>
  <div class="container">
    <Nav/>
  </div>
</template>

<style>
@import './assets/base.css';

.container {
  margin: 0 auto;
  max-width: 1200px;
  margin-bottom: 100px
}

/* Os breakpoints de todos os componentes estarão no componente principal */

@media (max-width: 480px) {

  .container {
    width: 300px;
  }

  .nav {
    margin-top: 25px;
    display: flex;
    flex-direction: column;
  }
 
  .nav__input {
    width: 100%;
    padding: 0;
    padding-left: 20px;
    margin: 0;
    margin-top: 10px;
    margin-bottom: 10px;
  }
  .nav__button {
    width: 100%;
    background: none;
  }

  p {
    text-align: center;
    margin-top: 10px;
  }

}


</style>
