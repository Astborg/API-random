<template>
  <div class="justify center m-14">
  <div>
    <h1 class="m-10 font-bold text-center text-xl">This is a random Blog page</h1>
  </div>
  <div v-if="quote" class="display-block text-center">
    <h5 class="m-2"><strong>ID: </strong> {{ quote.id }}</h5>
    <h2><strong>Title:  {{ quote.title }} </strong></h2>
    <h3 class="m-2"><strong>Body: </strong> {{ quote.body }}</h3>
  </div>
  <div class="text-center">
  <button @click="getData" class=" bg-orange-500 mt-8 font-semibold border-none rounded-lg p-4">Get a new blog</button>
</div>
</div>

</template>

<script setup>
import {ref} from 'vue'
let id = ref(0)
let title = ref('hallo')
let body = ref('random blogs')
const listItems = ref([])
let quote = ref(null)

async function getData(){
  const api = await fetch('https://jsonplaceholder.typicode.com/posts')
  const finalApi = await api.json()
  const index = Math.floor(Math.random()*finalApi.length)
  quote.value = finalApi[index]
 
  
}
</script>
