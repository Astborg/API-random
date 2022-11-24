<script setup>
import WelcomeItem from './WelcomeItem.vue'
</script>

<template>
  <WelcomeItem>

    <template #icon>
      <DocumentationIcon />
    </template>

    <template #heading>Random Quotes</template>
    <div>
      <h6>Writer</h6>
      <p>Random quotes here</p>
    </div>

  </WelcomeItem>
</template>
