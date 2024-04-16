<script>

import { store } from '../store.js'

export default {
    name: 'AppSearch',

    data() {
    return {
        store,

        avalaibleArchetype: []
    };
    },
}


</script>

<template>
   
    <div>    
        <select v-model="store.archetypeSelected" name="" id="">

            <option v-for="archetype in avalaibleArchetype" >type</option>
            

        </select>
    
    </div>
    
</template>

<style scoped lang="scss">
@use '../style/generic';



</style>