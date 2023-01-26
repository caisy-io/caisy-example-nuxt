<template>
  <h1>{{ route.params.slug }}</h1>
  <h1>{{ data.name }}</h1>
</template>

<script setup>
const route = useRoute();

const { data, error } = useFetch(`/api/getBlogBySlug/${route.params.slug}`);

console.log(error);
</script>
