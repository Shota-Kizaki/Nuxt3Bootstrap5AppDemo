<script setup lang="ts">
const name = useName()
</script>


<template>
  <NuxtLayout>
    <NuxtPage />
    <p>Hello {{ name }}</p>
  </NuxtLayout>
</template>
