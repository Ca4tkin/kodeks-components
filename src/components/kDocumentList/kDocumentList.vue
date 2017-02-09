<template>
  <ul class="document_lst">
    <li class="document_lst_i" v-for="document in documents">
      <a class="document_lst_lk" :href="'/document/' + document.id">
        <i class="document_lst_ic ic-doc" :class="{'ic-doc': document.status === 1, 'ic-doc-2': document.status === 2, 'ic-doc-3': document.status === 3}"></i>
        <div class="h __margin-bottom_xs" v-if="document.title">{{document.title}}</div>
        <div class="document_lst_dscr" v-if="document.description">{{document.description}}</div>
      </a>
    </li>
    <li class="document_lst_i">
      <div class="loader"></div>
    </li>
  </ul>
</template>

<script type="text/javascript">
export default {
  props: {
    docsList: Array
  },
  data () {
    return {
      documents: this.docsList
    }
  }
}
</script>

<style lang="sass" src="./style.sass">
</style>
