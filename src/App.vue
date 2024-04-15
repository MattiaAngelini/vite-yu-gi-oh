<script>
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import axios from 'axios'
import { store } from './store.js'

export default {
  components:{
  AppHeader,
  CharactersList
},

 data() {
  return {
    store
  };
 },

 methods: {
  getCharacterFromApi() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
    .then((response) =>{
      
      store.characters = response.data
      
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

      <CharactersList>

      </CharactersList>
    
  </main>
  
</template>

<style scoped lang="scss">
@use './style/generic' as *;
@use './partials/variables' as *;

main {background-color: $brand-primary;}

</style>
