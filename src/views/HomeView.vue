<template>
  <div class="about">
  <div>
    <h1 class="mb-6">This is a random Quote page</h1>
  </div>
  <div v-if="quote" class="justify-center flex flex-column text-center">
    <h5> ID: {{ quote.id }}</h5>
    <h3> Comment: {{ quote.body }}</h3>
  </div>
  <button @click="getData" class="bg-orange-500">Get a new quote</button>
  </div>

</template>

<script setup>
import {ref} from 'vue'
let id = ref(0)
let body = ref('random blogs')
const listItems = ref([])
let quote = ref(null)

async function getData(){
  const api = await fetch('https://jsonplaceholder.typicode.com/comments')
  const finalApi = await api.json()
  const index = Math.floor(Math.random()*finalApi.length)
  quote.value = finalApi[index]
 
  
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
