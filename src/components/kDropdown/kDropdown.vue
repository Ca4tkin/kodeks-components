<template>
  <transition name="fade">
    <div class="dropdown" v-if="show" :style="{width: width + 'px', top: top + 'px', left: left + 'px', right: right + 'px'}" :class="{__right: orientationRight}" v-on-clickaway="close">
      <slot></slot>
    </div>>
  </transition>
</template>

<script type="text/javascript">
import { mixin as clickaway } from 'vue-clickaway'

export default {
  mixins: [clickaway],
  props: {
    visible: Boolean,
    width: {
      type: String,
      default: '250'
    },
    top: {
      type: String,
      default: '30'
    },
    left: {
      type: String,
      default: '0'
    },
    right: {
      type: String,
      default: '0'
    },
    orientationRight: Boolean
  },
  data () {
    return {
      show: this.visible
    }
  },
  watch: {
    visible (val) {
      this.show = val
    }
  },
  methods: {
    close: function() {
      this.show = false
      this.$emit('close')
    }
  }
} 
</script>

<style lang="sass" src="./style.sass">
</style>
