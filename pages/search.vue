<script setup>
const search = ref("hello");
const { data, refresh } = await useAsyncData(
  ["search"].join(),
  () => searchContent(search, {}),
  { watch: [search] }
);
</script>

<template>
  <main>
    <input v-model="search" />

    <pre>{{ data }} </pre>
  </main>
</template>
