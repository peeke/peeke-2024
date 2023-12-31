<script setup>
const search = ref("hello");
const { data, refresh } = await useAsyncData(
  ["search", search.value].join(),
  () => searchContent(search, {})
);
</script>

<template>
  <main>
    <input v-model="search" />

    <pre>{{ data }} </pre>
  </main>
</template>
