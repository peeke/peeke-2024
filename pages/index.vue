<script setup>
const { data } = await useAsyncData("index", () =>
  queryContent("articles").sort({ _id: -1 }).find()
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
