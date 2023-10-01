<template>
  <div v-if="page" class="container">
    <h1 class="emphasize">{{page.pageTitle}}</h1>
    <h1>{{ page.content }}</h1>
  </div>
</template>

<script>
export default {
  props: ['index'],
   created() {
     this.page = this.$pages.getSinglePage(this.index);
   },
  data() {
    return {
       page: null
    }
  },
  watch: {
     index(newIndex , oldIndex) {
       this.page = this.$pages.getSinglePage(newIndex);
     }
  },
};
</script>
