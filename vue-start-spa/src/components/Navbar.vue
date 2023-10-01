<template>
  <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Navbar</a>
      <ul class="navbar-nav ne-auto nb-2 mb-lg-0">
          <navbar-link  v-for="(page, index) in publishedPages" class="nav-item" :key="index"      :page="page" :isActive="activePage == index"  :index="index" @actived="$emit('actived')"></navbar-link>

          <li>
            <router-link to="/create" class="nav-link" aria-current="page">Create Page</router-link>
          </li>
      </ul>

      <form class="d-flex">
        <button class="btn btn-primary" @click.prevent="changeTheme()">
          Toggle
        </button>
      </form>
    </div>
  </nav>
</template>

<script>
import NavbarLink from "./NavbarLink.vue";

export default {
  components: {
    NavbarLink,
  },
  created() {
    this.getThemeSetting();
  },
  computed: {
    publishedPages() {
       return this.pages.filter(p => p.published);
    }
  },
  props: ["pages", "activePage"],
  data() {
    return {
      theme: "light",
    };
  },
  methods: {
    changeTheme() {
      let theme = "light";

      if (this.theme == "light") {
        theme = "dark";
      }

      this.theme = theme;
      this.storeThemesetting();
    },
    storeThemesetting() {
       localStorage.setItem('theme' , this.theme);
    },
    getThemeSetting() {
       let theme = localStorage.getItem('theme');
       if(theme){
          this.theme = theme;
       }
    }
  },
};
</script>
