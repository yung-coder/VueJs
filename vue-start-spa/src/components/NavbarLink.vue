<template>
  <li>
    <router-link class="nav-link" active-class="active" aria-current="page" :to="`/${index}`"
    :title="`This link goes to the ${page.link.text} page`" @click.prevent="$bus.$emit('navbarLinkActived' , index)">{{ page.link.text }}</router-link>
  </li>
</template>

<script>
export default {
  props: ["page", "index"]
 };
</script>
