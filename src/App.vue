<script>
import InfoBeer from './components/InfoBeer.vue'
import axios from 'axios';
import { store } from "./store.js"

export default {
      components: {
        InfoBeer
      },
      data() {
		      return {
			        store,
		}
	},
  mounted() {

		  this.prova();
	},
  methods:{
      prova() {
        axios.get(this.store.apiUrl).then(risultato => {

          this.store.caratteristiche = risultato.data
          console.log(risultato.data[0].name)
        }) 

        
      }

  }



}
</script>

<template>
  
  <InfoBeer v-for="caratteristica in store.caratteristiche" :info="caratteristica" />

</template>

<style scoped>

</style>
