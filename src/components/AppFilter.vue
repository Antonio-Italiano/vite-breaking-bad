<script>
import { store } from '../data/store'
export default {
    name: 'AppFilter',
    data() {
        return {
            store,
            choice: '',
        }

    },
    emits: ['choice-clicked', 'reset'],
    methods: {
    }
}
</script>

<template>
    <div class="container d-flex">

        <select v-model="choice" @change="$emit('choice-clicked', this.choice)" name="select-object" id="select">
            <option v-for="p in store.types1" :value="p">{{ p }}</option>
        </select>
        <button class="btn btn-danger ms-3" @click="$emit('reset')">Reset</button>

    </div>
</template>

<style lang="scss" scoped>

</style>