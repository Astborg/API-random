<template>
  <div class="about">
  <div>
    <h1 class="mb-6">This is a random Blog page</h1>
  </div>
  <div v-for="item in listItems" class="justify-center flex flex-column text-center">
    <h5> ID: {{ item.id }}</h5>
    <h2> Title: {{ item.title }}</h2>
    <h3> Body: {{ item.body }}</h3>
  </div>
  <button @click="getData()" class="bg-orange-500">Get a new blog</button>
  </div>

</template>

<script setup>
import {ref} from 'vue'
const id = ref(0)
const title = ref('hallo')
const body = ref('random blogs')
const listItems = ref([])

async function getData(){
  const api = await fetch('https://jsonplaceholder.typicode.com/posts')
  const finalApi = await api.json()
  listItems.value = finalApi
  
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
