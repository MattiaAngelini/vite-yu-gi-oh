<script>
export default {
    name: 'SingleCharacter',

    props:  {
        characterDetails: Object
    }
}
</script>

<template>
    <div class="card">           
        <img :src="characterDetails.card_images[0].image_url">
        <div class="info-card d-flex flex-column align-items-center">
            <div> {{ characterDetails.name }} </div> 
            <div> {{ characterDetails.type }} </div> 
        </div>
          
    </div>
</template>

<style scoped lang="scss">
@use '../style/generic' as *;
@use '../partials/variables' as *;

.card { 
    width: calc(100%/5 - 20px);
    margin: 10px;
    padding: 10px;
}

</style>