<template>
  <div class="about">
  <div>
    <h1 class="mb-6">This is a random Quote</h1>
  </div>
  <div v-if="quote" class="justify-center flex flex-column text-center">
    <h2> {{ quote }}</h2>
    <h4>- Kanye West</h4>

  </div>
  <button @click="getData" class="bg-orange-500">Get a new quote</button>
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
