<template>
  <navbar :pages="pages" :active-page="activePage"></navbar>

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
  created() {
    this.getPages();

    this.$bus.$on('navbarLinkActived', (index) => {
      this.activePages = index;
    });
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
      this.pages.push(pageObj);
    }
  },
};
</script>
