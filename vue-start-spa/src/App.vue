<template>
  <navbar
    :pages="pages"
    :active-page="activePage"
    :nav-link-click="(index) => (activePages = index)"
  ></navbar>

  <page-viewer :page="pages[activePages]"></page-viewer>
</template>

<script>
import Navbar from "./components/Navbar.vue";

import PageViewer from "./components/PageViewer.vue";

export default {
  components: {
    Navbar,
    PageViewer,
  },
  data() {
    return {
      activePages: 0,
      pages: [
        {
          link: { text: "Home", url: "index.html" },
          pageTitle: "Home Page",
          content: "This is the home content",
        },
        {
          link: { text: "About", url: "about.html" },
          pageTitle: "About Page",
          content: "This is the About content",
        },
        {
          link: { text: "Contact", url: "contact.html" },
          pageTitle: "Contact Page",
          content: "This is the contact content",
        },
      ],
    };
  },
};
</script>
