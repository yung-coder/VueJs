<template>
  <li>
    <router-link class="nav-link" :class="activeClasses" aria-current="page" :to="`/${index}`"
    :title="`This link goes to the ${page.link.text} page`" @click.prevent="$bus.$emit('navbarLinkActived' , index)">{{ page.link.text }}</router-link>
  </li>
</template>

<script>
export default {
  props: ["page", "index", "isActive"],
  computed: {
    activeClasses() {
      return {
        active: this.isActive,
        emphasize: this.isActive,
      };
    },
  },
};
</script>

<style>
.emphasize {
  text-decoration: underline !important;
}
</style>
