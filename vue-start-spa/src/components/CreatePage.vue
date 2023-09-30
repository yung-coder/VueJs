<template>
  <div class="container nb-3">
    <form action="">
      <div class="mb-3">
        <label for="" class="form-label">
          Page Title
        </label>
        <input type="text" class="form-control"   v-model="pageTitle" />
      </div>
      <div class="mb-3">
        <label for="" class="form-label">
          Content
        </label>
        <textarea type="text" class="form-control" rows="5" v-model="content"></textarea>
      </div>
      <div class="mb-3">
        <button class="btn btn-primary" @click.prevent="pageCreated({ pageTitle , content })">Sumbit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  props: ['pageCreated'],
  data() {
    return {
      pageTitle: '',
      content: ''
    }
  },
}
</script>
