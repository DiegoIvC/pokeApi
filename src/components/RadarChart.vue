<script setup>
import {computed} from "vue";


const propiedades = defineProps({
  stats:Array
})
const options ={
  chart: {
    id: 'vuechart-example'
  },
  xaxis: {
    categories: ['PV', 'Ataque', 'Defensa', 'Ataque ES', 'Defensa ES', 'Velocidad']
  }
}
const series= computed(()=> {
  return [
    {
      name:'Estadistica',
      data:propiedades.stats
    }
  ]
})


</script>

<template>
  <div>
    <apexchart width="500" type="radar" :options="options" :series="series"></apexchart>
  </div>
</template>

<style scoped>

</style>