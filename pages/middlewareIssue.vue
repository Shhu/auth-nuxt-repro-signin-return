<script setup lang="ts">
definePageMeta({
  middleware: 'auth' // Type '"auth"' is not assignable to type '"test" | NavigationGuard | ("test" | NavigationGuard)[] | undefined'.
})
</script>

<template>
  <div></div>
</template>