<template>
    <button @click="$emit('click', -1)">Anterior</button>
    <button @click="$emit('click', 1)">Següent</button> 
    <!-- pasar evento y parametro -->
</template>

<script>
export default {
    name: "ButtonsComponent", 
    emits: ['click'] //solo para definir el evento a emitir
}
</script>

<style scoped lang="css">
    button {
        font-size: 1.7em;
        background-color: white;
        padding:15px;
        margin-bottom: 15px;
        border:solid 1px;
        border-color:black;
        width: 50%;
    }
    p {
        text-align: center;
    }
</style>