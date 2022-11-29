<template>
  <div class="about">
  <div>
    <h1 class="m-10 font-bold text-center text-xl">This is a random Quote</h1>
  </div>
  <div v-if="quote" class="display-block text-center">
    <h2><strong class="text-xl">"</strong>  {{ quote }}<strong class="text-xl">"</strong>  </h2>
    <h4 class="mt-4 font-semibold">- Kanye West</h4>

  </div>
  <div class="text-center">
  <button @click="getData" class="bg-orange-500 mt-8 font-semibold border-none rounded-lg p-4">Get a new quote</button>
</div>
</div>

</template>

<script setup>
import {ref} from 'vue'
import axios from 'axios'

let quote = ref('')

function getData(){
  axios.get('https://api.kanye.rest/')
  .then(response =>{
    quote.value = response.data.quote
  })
}

  

</script>

<style>
@media (min-width: 1024px) {
  .about {
    
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
</style>
