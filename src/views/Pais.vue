<template>
  <h1>Detalle {{nombre}}</h1>
  <p v-for="(pais, index) in arrayData" :key="index">
    {{pais.name}} - {{pais.region}}
  </p>
</template>

<script>
import { useRoute } from 'vue-router';
import { useFetch } from '../hooks/useFetch'
export default {

  props: ['nombre'],

  setup(props){
      
      const nombreParams = useRoute()

      const {arrayData} = useFetch(`https://restcountries.eu/rest/v2/name/${nombreParams.params.nombre}`)

      return{arrayData}
  }
}
</script>

<style>

</style>