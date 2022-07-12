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
</style>
