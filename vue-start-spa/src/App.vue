<template>
  <navbar :pages="pages" :active-page="activePage" :nav-link-click="(index) => (activePages = index)"></navbar>

  <!-- <page-viewer :page="pages[activePages]"></page-viewer> -->

  <create-page :page-created="pageCreated"></create-page>``
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
  created() {
    this.getPages();
  },
  data() {
    return {
      activePages: 0,
      pages: []
    };
  },
  methods: {
    async getPages() {
      let res = await fetch('pages.json');
      let data = await res.json();

      this.pages = data;
    },
    pageCreated(pageObj) {
      console.log(pageObj);
    }
  },
};
</script>
