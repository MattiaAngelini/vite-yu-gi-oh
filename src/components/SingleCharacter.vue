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
        <div class="info-card d-flex flex-column justify-content-between align-items-center p-3">
            <div class="text-white"> {{ characterDetails.name }} </div> 
            <div> {{ characterDetails.type }} </div> 
        </div>
          
    </div>
</template>

<style scoped lang="scss">
@use '../style/generic' as *;
@use '../partials/variables' as *;

.card { 
    width: calc(100%/5 - 40px);
    margin: 0 20px 20px 20px; 
    background-color: $brand-primary;

        .info-card {
            height: 150px;
        }

        .text-white {
            font-weight: 800;
            max-width: 100%;
        }
}

</style>