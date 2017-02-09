<template>
  <ul class="document_lst">
    <li class="document_lst_i" v-for="document in documents">
      <a class="document_lst_lk" :href="'/document/' + document.id">
        <i class="document_lst_ic" :class="{'ic-doc': document.status === 1, 'ic-doc-2': document.status === 2, 'ic-doc-3': document.status === 3}"></i>
        <div class="h __margin-bottom_xs">{{document.name}}</div>
        <div class="document_lst_dscr">{{document.description}}</div>
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
    myData: Array
  },
  data () {
    return {
      documents: this.myData
    }
  }
}
</script>

<style lang="sass" src="./style.sass">
</style>
