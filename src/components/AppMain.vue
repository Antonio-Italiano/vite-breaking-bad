<script>
import AppPokemonCard from './AppPokemonCard.vue'
export default {
    name: 'AppMain',
    data() {
        return {
        }
    },
    components: {
        AppPokemonCard
    }
}
</script>

<template>
    <main class="container text-center mt-5">
        <h1>Pokévue</h1>
        <div class="content p-3 mt-3">
            <app-pokemon-card></app-pokemon-card>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.container {

    .content {
        height: 80vh;
        width: 80vw;
        border: 10px solid rgb(10, 65, 7);
    }
}
</style>