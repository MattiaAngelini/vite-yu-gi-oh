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
        <select @change="$emit('searchCards')" v-model="store.archetypeSelected" name="" id="">

            <option  v-for="archetype in store.archetype" :value="archetype.archetype_name" >{{ archetype.archetype_name }} </option>
        
        </select>  
    </div>
    
</template>

<style scoped lang="scss">
@use '../style/generic';





</style>