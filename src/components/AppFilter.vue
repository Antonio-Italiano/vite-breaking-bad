<script>
import { store } from '../data/store'
export default {
    name: 'AppFilter',
    data() {
        return store
    },
    components: {
    }
}
console.log(store.types1)
</script>

<template>
    <select name="select-object" id="select">
        <option v-for="p in types1" :value="p">{{ p }}</option>
    </select>
</template>

<style lang="scss" scoped>

</style>