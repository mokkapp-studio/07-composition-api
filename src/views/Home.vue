<template>
  <div class="home">
    <Titulo :contador="contador" />
    <h1 :style="{'color': color}">Contador: {{contador}}</h1>
    <button type="button" @click="mas">Mas</button>
    <button type="button" @click="menos">Menos</button>
  </div>
</template>

<script>
import Titulo from '../components/Titulo.vue'


export default {
  name: 'Home',
  components: {
    Titulo
  },
  data() {
    return {
      contador: 0
    }
  },
  computed: {
    color(){
    if(this.contador < 0){
      return 'red'
    }else{
      return 'blue'
    }
    }
  },
  methods: {
    mas(){
      this.contador ++
    },
    menos(){
      this.contador --
    }
  },
}
</script>
