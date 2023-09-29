<template>
  <div class="container">
    <h1 class="emphasize">{{ page.pageTitle }}</h1>
    <h1>{{ page.content }}</h1>
  </div>
</template>

<script>
export default {
  props: ["page"],
};
</script>
