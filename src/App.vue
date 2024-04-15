<script>
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';

export default {
  components:{
  AppHeader,
  CharactersList
  
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
