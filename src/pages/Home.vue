<script setup>
import {reactive, toRef, toRefs, computed} from "vue";

  const state = reactive({
    pokemons:[],
    name:'',
    filterPokemon: computed(()=>searchPokemon())
  })
  function searchPokemon(){
    return state.pokemons.filter((pokemon)=>pokemon.name.includes(state.name.toLowerCase()))
  }
  const { name, filterPokemon} = toRefs(state)

  fetch('http://pokeapi.co/api/v2/pokemon?limit=151')
  .then((res)=>res.json())
  .then((data)=>{
    console.log(data)
    data.results.forEach((element, index)=>{
      const pokemon = {
        ...element,
        index:index+1
      }
      state.pokemons.push(pokemon)
    })
  })
</script>

<template>
  <div class="grid grid-cols-6 gap-1">
    <div class="col-span-1">
      <div class="col-span-1">
        <input
            type="text"
            class="mb-3 mt-3 p-2 shadow-md border-2  focus:border-blue-700 focus:ring-2 focus:ring-blue-300 w-full rounded-md"
            placeholder="Escribe el nombre del Pokémon"
            v-model="name">
      </div>
      <ul class="overflow-y-auto max-h-96">
        <li v-for="pokemon in filterPokemon" :key="pokemon.index"
            class="p-2 rounded hover:text-blue-400 hover:bg-blue-100"
        >
          <span class="text-sm font-normal text-gray-400 m-3"> #{{pokemon.index}}</span>
          <router-link :to="`/details/${pokemon.index}`">{{ pokemon.name }}</router-link>

        </li>
      </ul>
    </div>
    <div class="col-span-5">
      <router-view></router-view>
    </div>
  </div>

</template>

