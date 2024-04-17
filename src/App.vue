<script>
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import AppLoader from './components/AppLoader.vue'
import AppSearch from './components/AppSearch.vue'
import axios from 'axios'
import { store } from './store.js'

export default {
  components:{
  AppHeader,
  CharactersList,
  AppLoader,
  AppSearch
},

 data() {
  return {
    store,
   
  };
 },

 methods: {

  //CHIAMATE API
  getCharacterFromApi() {
    console.log(store.archetypeSelected)
    let apiUrl =  'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0';

    const queryParams= {
      num:20,
      offset:0
    };
    
    // se contenuto inserito da utente diverso da zero, l'archetipo delle query params
    // sarà uguale al valore scelto dall'utente per filtrare le cards
    if(store.archetypeSelected !== ''){
      queryParams.archetype = store.archetypeSelected;
    }
    
    //chiamata axios con parametri
    axios.get(apiUrl, 
    {params: queryParams

    })

    .then((response) =>{
      // dopo chiamata api popolo array nello store.js per avere oggetti a disposizione.
      store.characters = response.data
      // ottenuto i dati, la var isLoading diventa false. (per comparsa/scomparsa elemento con img loading)
      store.isLoading = false;
    } );
  
  },

  getArchetypeFromApi() {

    let apiUrl = 'https://db.ygoprodeck.com/api/v7/archetypes.php';

    axios.get(apiUrl)
    .then((response) =>{  
      store.archetype = response.data;
    } );
  },
 },

 mounted() {
  this.getCharacterFromApi();
  this.getArchetypeFromApi();
 }
}

</script>

<template>

  <AppHeader></AppHeader>

  <main>
        <AppSearch @searchCards="getCharacterFromApi" class="p-3"></AppSearch>
        <CharactersList v-if="store.isLoading === false">  </CharactersList>
        <AppLoader v-else></AppLoader>
  </main>
  
</template>


<style scoped lang="scss">
@use './style/generic' as *;
@use './partials/variables' as *;

main {background-color: $brand-primary;}
</style>
