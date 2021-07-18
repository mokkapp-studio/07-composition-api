<template>
  <h1 :style="{'color': color}">Contador: {{signo}}</h1>
</template>

<script>
import { computed } from 'vue'

export default {
    props: ['contador', 'color'],

    // computed: {
    //     signo(){
    //         return '$' + this.contador
    //     }
    // }

    setup(props){
        const signo = computed(() => {
            return '$' + props.contador
        })
        return {
            signo
        }
    }
}
</script>

<style>

</style>