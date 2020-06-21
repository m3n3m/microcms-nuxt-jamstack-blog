<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <p class="category">{{ category && category.name }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from "axios";

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://nelnelium.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: { "X-API-KEY": "c6700455-dc9f-4be0-b156-05716d0a5576" }
      }
    );
    return data;
  }
};
</script>
