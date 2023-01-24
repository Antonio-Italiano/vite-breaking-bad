<script>
export default {
    name: 'AppPokemonCard',
    data() {
        return {
        }
    },
    props: {
        pokemon: Array,
    }
}
</script>

<template>
    <div class="container">
        <div class="row row-cols-2 row-cols-md-5 row-cols-lg-5">
            <div v-for="p in pokemon" class="col">
                <img :src="p.imageUrl" :alt="p.name">
                <h6 class="mt-2">{{ p.name }}</h6>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container {
    height: 100%;
    width: 100%;

    .row {
        height: 100%;
        width: 100%;
        gap: 15px;

        .col {
            width: calc(20% - 12px);
            border: 2px solid rgba(175, 255, 100, 0.444);
            background-color: rgba(106, 106, 106);
            padding: 10px;

            &.col:hover {
                scale: 1.1;
                background-color: rgba(91, 91, 91);

            }

            img {
                width: 100%;
            }
        }
    }
}
</style>