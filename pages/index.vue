<script setup>
const { data } = await useAsyncData("index", () =>
  queryContent().sort({ _id: -1 }).only(['_path', 'title']).find()
);

</script>

<template>
  <pre>{{ data }}</pre>
  <ul>
    <li v-for="article in data" :key="article._id">
      <NuxtLink :to="article._path">{{ article.title }}</NuxtLink>
    </li>
  </ul>
</template>
