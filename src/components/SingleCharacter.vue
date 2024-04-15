<script>
export default {
    name: 'SingleCharacter'
}
</script>

<template>
    <div class="card">           
        <img src="https://images.ygoprodeck.com/images/cards_small/34541863.jpg" alt="">
        <div class="info-card d-flex flex-column align-items-center">
            <div>CARTA</div> 
            <div>TIPO</div> 
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