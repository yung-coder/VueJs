<template>
  <navbar></navbar>

  <router-view></router-view>
  <!-- 
  <page-viewer v-if="pages.length >0" :page="pages[activePages]"></page-viewer>

  <create-page @page-created="pageCreated"></create-page> -->
</template>

<script>
import CreatePage from "./components/CreatePage.vue";
import Navbar from "./components/Navbar.vue";

import PageViewer from "./components/PageViewer.vue";

export default {
  components: {
    Navbar,
    PageViewer,
    CreatePage
  },
  
  methods: {
    pageCreated(pageObj) {
      this.pages.push(pageObj);
    }
  },
};
</script>
