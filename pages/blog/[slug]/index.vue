<template>
  <RichtextRenderer
    v-if="data?.text && data?.text?.json"
    :node="data.text.json"
  />
  <div v-else>
    <h1>
      Document with slug <em>"{{ route.params.slug }}"</em> was not found
    </h1>
  </div>
</template>

<script setup>
import { RichtextRenderer } from "@caisy/rich-text-vue-renderer";
const route = useRoute();

const { data } = useFetch(`/api/blog/${route.params.slug}`);
</script>
