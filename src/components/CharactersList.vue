<script>
import SingleCharacter from './SingleCharacter.vue';
import { store } from '../store.js';

export default {
    name: 'CharactersList',
    components: {
        SingleCharacter
    },

    data(){
        return {
            store
        }
    }
}
</script>

<template>

    <section>    
        <div class=" container-card d-flex flex-wrap justify-content-betweeen">
      
            <SingleCharacter v-for="character in store.characters.data" key="characters.data.id" 
            :characterDetails="character"></SingleCharacter>
              
        </div> 
    </section>

</template>

<style scoped lang="scss">
@use '../style/generic' as *;
@use '../partials/variables' as *;

section {
    padding: 40px;
    
        .container-card {
            border: 40px solid white;
        
        }
}

</style>