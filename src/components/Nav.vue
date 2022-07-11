<script>
  import Github from '@/components/icons/Github.vue'

  export default {
    components: { Github }
  }

</script>

<template>
  <div class="nav">
    <div class="nav__label">
      <Github class="nav__label__icon"/>
      <strong> GET</strong>hub.
    </div>
    <input class="nav__input" placeholder="Digite aqui o nome do perfil">
    <button class="nav__button">Buscar</button>
  </div>
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
</style>
