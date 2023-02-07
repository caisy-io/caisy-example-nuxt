<template>
  <div v-if="data?.text && data?.text?.json">
    <h1>{{ data.title }}</h1>
    <RichTextRenderer :node="data.text.json" />
  </div>
  <div v-else>
    <h1>Loading...</h1>
  </div>
</template>

<script setup>
import { RichTextRenderer } from "@caisy/rich-text-vue-renderer";
const route = useRoute();

const { data } = useFetch(`/api/blog/${route.params.slug}`);
</script>
