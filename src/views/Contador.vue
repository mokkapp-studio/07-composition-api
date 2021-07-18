<template>
    <h1>Contador{{contador}}</h1>
    <Btn 
      @evento="aumentar" 
      :textoBotton="'Aumentar'"/>
    <Btn 
      @evento="disminuir" 
      :textoBotton="'Disminuir'"/>
</template>

<script>
import Btn from '../components/Btn.vue';
import { useContador } from '../hooks/useContador';

export default {
  components: { Btn },
  setup(){
      return {...useContador()}
  }
}
</script>

<style>

</style>