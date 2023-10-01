<template>
  <div v-if="page" class="container">
    <h1 class="emphasize">{{page.pageTitle}}</h1>
    <h1>{{ page.content }}</h1>
  </div>
</template>

<script>
export default {
   created() {
     this.page = this.$pages.getSinglePage(this.$route.params.index);
   },
  data() {
    return {
       page: null
    }
  },
};
</script>
