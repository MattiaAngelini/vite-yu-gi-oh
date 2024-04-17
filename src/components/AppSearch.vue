<script>

import { store } from '../store.js'

export default {
    name: 'AppSearch',

    data() {
    return {
        store,
        
    };
    },
}


</script>

<template>
   
    <div>    
        <select v-model="store.archetypeSelected" name="" id="">

            <option v-for="archetype in store.archetype">{{ archetype.archetype_name }} </option>
        
        </select>  
    </div>
    
</template>

<style scoped lang="scss">
@use '../style/generic';





</style>