<script>
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import AppLoader from './components/AppLoader.vue'
import axios from 'axios'
import { store } from './store.js'

export default {
  components:{
  AppHeader,
  CharactersList,
  AppLoader
},

 data() {
  return {
    store
  };
 },

 methods: {
  //CHIAMATA API
  getCharacterFromApi() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
    .then((response) =>{
      
      // dopo chiamata api popolo array nello store.js per avere oggetti a disposizione.
      store.characters = response.data
      // ottenuto i dati, la var isLoading diventa false. (per comparsa/scomparsa elemento con img loading)
      store.isLoading = false;
      
    } );
    
  }
 },

 mounted() {
  this.getCharacterFromApi();
 }
}

</script>

<template>

  <AppHeader></AppHeader>

  <main>
        <CharactersList v-if="store.isLoading === false">  </CharactersList>
        <AppLoader v-else></AppLoader>
  </main>
  
</template>


<style scoped lang="scss">
@use './style/generic' as *;
@use './partials/variables' as *;

main {background-color: $brand-primary;}
</style>
