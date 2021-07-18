<template>
  <!-- <button @click="$emit('accion')">{{textoBotton}}</button> -->
  <button @click="accion">{{textoBotton}}</button>
</template>

<script>
export default {
    name: 'Btn',
    props: ['textoBotton'],
    setup(props, context){
        const accion = () => {
            context.emit('evento')
        }

        return{
            accion
        }
    }
}
</script>
