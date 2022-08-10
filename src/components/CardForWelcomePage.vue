<template>
    <div class="card__welcome">
        <div class="subtitle">
            <p>Liste os <strong class="subtitle__strong">repositórios </strong> do seu perfil <strong
                    class="subtitle__strong">Git</strong> favorito,<br /> obtenha informações sobre commits, datas e
                mais, através do <strong class="subtitle__strong">GET</strong>hub ;)
            </p>
        </div>
    </div>
</template>
<script>
</script>
<style>

.card__welcome {
    box-sizing: border-box;
    margin: 0 auto;
    margin-top: 40px;
    width: 100%;
    height: fit-content;
    animation: fade-in 1000ms;
    animation-iteration-count: 1;
    padding-bottom: 27px;
    
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


@keyframes fade-in {
    from {
        
        opacity: 0.1;
    }

    to {
        
        opacity: 1;
    }
}
</style>