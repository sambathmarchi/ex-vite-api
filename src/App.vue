<script>
  import AppCard from "./components/AppCard.vue"
  import { store } from "../store.js"
  import AppSearchComp from "./components/AppSearchComp.vue";
  import axios from 'axios';
  
  
  export default{
    components: {
      
      AppCard,
      AppSearchComp

    },
    data() {
        return{
          pubs: [],
          store
        }
      },
  
  methods: {
    getBeer() {

      axios.get('https://api.openbrewerydb.org/v1/breweries?by_country=austria&per_page=10').then(risultato =>{
        this.pubs.push(...risultato.data)
        console.log(this.pubs)
          
          
      })
    },
    getInfos(){
      this.pubs = []
      axios.get(`https://api.openbrewerydb.org/v1/breweries?by_name=${store.searchString}&per_page=10`).then(risultato => {
        this.pubs.push(...risultato.data)
      })
      

    }
  },
  mounted(){
    this.getBeer();
  }
};
  
  
 
</script>

<template>
    <AppSearchComp @searching="getInfos" />
    <AppCard :arrayGenerato="pubs" />
</template>

<style scoped>
  
</style>
