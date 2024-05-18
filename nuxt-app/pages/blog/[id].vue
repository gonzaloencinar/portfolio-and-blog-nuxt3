<template>
  <div>We are inside a blog post!</div>
  <div>Post ID: {{ route.params.id }}</div>
</template>

<script setup>
const route = useRoute();
console.log(route);
</script>
