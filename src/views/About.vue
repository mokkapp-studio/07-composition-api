<template>
  <div class="about">
    <Titulo 
      :contador="contador"
      :color="color"
    />
    <!-- <h1 :style="{'color': color}">Contador: {{contador}}</h1> -->
    <!-- <button @click="aumentar">mas</button>
    <button @click="disminuir">menos</button> -->
    <Btn 
      @evento="aumentar" 
      :textoBotton="'Aumentar'"/>
    <Btn 
      @evento="disminuir" 
      :textoBotton="'Disminuir'"/>
    <hr>
    <input type="text" v-model="texto">
    <p>{{texto}}</p>
  </div>
</template>


<script>
import { computed, ref } from 'vue';
import Titulo from '../components/Titulo.vue';
import Btn from '../components/Btn.vue'

export default {

      components: {
        Titulo,
        Btn
      },

      setup(){

        const texto = ref('');
        const contador = ref(0);

        const aumentar = () => {
            contador.value ++
        }

        const disminuir = () => {
            contador.value --
        }

        const color = computed(() =>{
          if(contador.value < 0){
            return 'red'
          }else{
            return 'blue'
          }
        })

        return { 
            contador,
            color,
            texto,
            aumentar,
            disminuir,
        }
    }
}
</script>