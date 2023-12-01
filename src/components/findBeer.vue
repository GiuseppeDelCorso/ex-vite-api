<script>
import { store } from "../store.js"

export default{
    name: "findBeer",
    data(){
        return{
            store
        }
    },
    methods: {
        search(){
            console.log("Cerca: ", this.store.findString)
            this.$emit("search")
        }
    },
    mounted(){
        
    }
}

</script>

<template>

    <div>
        
        <input v-model="store.findString" placeholder="Cerca..." @keyup.enter="$emit('search')">
        <button @click="search">Cerca</button>
    
    </div>
   

</template>

<style scoped></style>



