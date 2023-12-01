<script>
import InfoBeer from './components/InfoBeer.vue'
import findBeer from './components/findBeer.vue'
import axios from 'axios';
import { store } from "./store.js"

export default {
      components: {
        InfoBeer,
        findBeer
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
         
        let link = this.store.apiUrl
        console.log(this.store.findString)

          if(this.store.findString == ""){
            
            console.log(this.store.findString)
            
            axios.get(link).then(risultato => {
            this.store.caratteristiche = risultato.data
            console.log("sono if")
          }) 
          }

          else{
            axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=austria&per_page=10&by_name=" + this.store.findString).then(risultato => {
              this.store.caratteristiche = risultato.data
              console.log(risultato.data)
              console.log("sono else")
            }) 

          }                   
      }
  }
}
</script>

<template>
  <main>
    <findBeer @search="prova" />
  </main>
  <header>
    <InfoBeer v-for="caratteristica in store.caratteristiche" :info="caratteristica" />
    
  </header>
</template>

<style scoped>

</style>
