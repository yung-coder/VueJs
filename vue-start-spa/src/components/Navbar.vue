<template>
  <nav  
      :class="[`navbar-${theme}` , `bg-${theme}` , 'navbar' , 'navbar-expand-lg']"
    >
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Navbar</a>
      <ul class="navbar-nav ne-auto nb-2 mb-lg-0">
        <li v-for="(page , index) in pages" class="nav-item" :key="index">
            <a 
              class="nav-link"
              :class ="{active: activePage == index}"
              aria-current="page"
              :href="page.link.url"
            :title="`This link goes to the ${page.link.text} page`"
              @click.prevnet="navlinkClick(index)"
            >{{page.link.text}}</a>
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
export default {
   props: ['pages', 'activePage' , 'navlinkclick'],
   data() {
      return {
         theme: 'light',
      }
   }, 
   methods: {
     changeTheme() {
        let theme = 'light';
        
        if(this.theme == 'light') {
           theme = 'dark';
        }

        this.theme = theme;
     }
   }
}
</script>
