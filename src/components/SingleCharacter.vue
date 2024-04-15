<script>
export default {
    name: 'SingleCharacter'
}
</script>

<template>
    <div class="card">singola carta</div>
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