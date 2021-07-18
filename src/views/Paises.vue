<template>
  <h1>Paises</h1>
  <p v-for="(pais, index) in arrayData" :key="index">
      <router-link :to="`/paises/${pais.name}`">
          {{pais.name}}
      </router-link>
  </p>
</template>

<script>
import {useFetch} from '../hooks/useFetch'
export default {
    setup(){

        // const arrayData = ref([])

        // const fetchData = async() => {
        //     try {
        //         // const res = await fetch('api.json')
        //         const res = await fetch('https://restcountries.eu/rest/v2/all')
        //         arrayData.value = await res.json()
        //         console.log(arrayData.value)
        //     } catch (error) {
        //         console.log(error)
        //     }
        // }
        // fetchData()

        // return{
        //     arrayData
        // }

        // se puede poner la URL: https://restcountries.eu/rest/v2/all o la data que viene de public
        return{...useFetch('api.json')}

    }

}
</script>

<style>

</style>