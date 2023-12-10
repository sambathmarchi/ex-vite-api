<script>
 import { store } from "../../store.js"
    export default{
        data(){

            return{
                store
            }
        },
        methods: {
            searchInput() {
                this.$emit("searching")
            }
        }
    }
</script>

<template>
    <div>
        <input v-model="store.searchString" type="text" placeholder="CERCA" @keyup.enter="searchInput">
        <button @click="searchInput">VAI</button>
    </div>
</template>

<style scoped>
    div{
        width: 200px;
        margin: 2rem auto;

    }
</style>