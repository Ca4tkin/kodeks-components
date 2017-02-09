<template>
  <div id="app">
    <img src="./assets/logo.png">
    
    <k-modal :visible="showModal" @close="showModal = false">First Modal</k-modal>
    <k-modal :visible="showModalSecond" @close="showModalSecond = false">Second Modal</k-modal>
    
    <a href="" @click.prevent="showModal = true">Тест 1</a>
    <a href="" @click.prevent="showModalSecond = true">Тест 2</a>
    <div>
    <a href="" @click.prevent="showDropdown = !showDropdown">Тест 3
    </a>
    <k-dropdown :visible="showDropdown" @close="showDropdown = false">klgklfdfgldlk</k-dropdown>
    </div>
    <k-document-list :docs-list="documents"></k-document-list>

  </div>
</template>


<script>
import kModal from './components/kModal/kModal.vue'
import kDropdown from './components/kDropdown/kDropdown.vue'
import kDocumentList from './components/kDocumentList/kDocumentList.vue'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      showModal: false,
      showModalSecond: false,
      showDropdown: false,
      documents: [{name: 'doc1', description: 'description1', status: 1, id: '1111'}, {name: 'doc2', description: 'description2', status: 2, id: '2222'}, {name: 'doc5', description: 'description3', status: 3, id: '3333'}]
    }
  },
  components: {
    kModal, kDropdown, kDocumentList
  }
}
</script>

<style lang="css" src="kodeks-components/src/components/styles/fonts.css"></style>
<style lang="sass" src="./components/styles/base.sass"></style>
