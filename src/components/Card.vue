<script>
import Github from '@/components/icons/Github.vue';
import Link from '@/components/icons/Link.vue'
export default {

    data() {
        return {

        }
    },
    components: { Github, Link },
    props: ['repoData'],
    filters: {
        valuefilter(value) {
            return '$' + value
        }
    }
}

</script>
<template>
    <div class="card">
        <div class="card__content">
            <div>
                <h3 class="card__content__title">{{ repoData.name }}</h3>
            </div>
            <div>
                <p class="card__content__datas__description"><strong>Data de criação: {{
                        Intl.DateTimeFormat('pt-br').format(new Date(repoData.created_at))
                }}</strong>
                <div class="card__content__data"></div>
                </p>
            </div>
            <div>
                <p class="card__content__datas__description"><strong>Ultima Atualização: {{
                        Intl.DateTimeFormat('pt-br').format(new Date(repoData.updated_at))
                }}</strong>
                <div class="card__content__data"></div>
                </p>
            </div>
            <div>
                <p class="card__content__description">
                    {{ repoData.description }}
                </p>
            </div>
            <div class="card__icon">
                <div id="card__icon__animation">
                    <a v-bind:href="repoData.html_url" target="__blank">
                        <Link class="card__icon__link" alt="Seguir link" />
                    </a>
                    <div id="card__icon__underline"></div>
                </div>
            </div>
        </div>
    </div>
</template>
<style>
.card {
    box-sizing: border-box;
    margin: 0 auto;
    margin-top: 35px;
    max-width: 1100px;
    height: fit-content;
    box-shadow: var(--shadow-dark);
    animation: slide-in 1000ms;
    animation-iteration-count: 1;
    padding: 15px;
}

.card__message {
    position: relative;
    box-sizing: border-box;
    display: flex;
    font-family: 'poppins', sans-serif;
    color: var(--fifth-dark);
    text-align: center;
    padding: 10px 15px;
}

.card__content {
    font-family: 'poppins', sans-serif;
}

.card__content__title {
    margin-top: 0;
    font-size: 20px;
    color: var(--third-dark);
}

.card__content__description {
    margin-top: 10px;
    color: var(--third-dark);
}

.card__content__datas__description {
    display: inline;
    color: var(--fifth-dark);
}

.card__content__data {
    display: inline;
    margin-left: 8px;
    font-style: italic;
    color: var(--third-dark);
}

p {
    margin-bottom: 0;
}

.card__icon {
    display: flex;
    justify-content: end;
    margin-top: 15px;
    fill: none;
}

.card__icon__link {
    stroke: var(--fifth-dark);
}

.card__icon__link:hover {
    stroke: var(--third-dark);
}


#card__icon__animation {
    position: relative;
    overflow: hidden;
    cursor: pointer;
}

#card__icon__animation a {
    position: relative;
    transition: all 4s ease-Out;
}

#card__icon__underline {
    width: 100%;
    height: 2.5px;
    margin-top: 15px;
    align-self: flex-end;
    left: -200px;
    background: var(--third-dark);
    position: absolute;
    transition: all .4s ease-Out;
    bottom: 0;
}

#card__icon__animation:hover #card__icon__underline {
    left: 0;
}

@keyframes slide-in {
    from {
        transform: translateX(-100%);
        opacity: 0.1;
    }

    to {
        transform: translateX(0%);
        opacity: 1;
    }
}

@media (max-width: 480px) {

.card__content {
    text-align: center;
}

.card__content__description {
    font-size: 15px;
}
  
}

</style>