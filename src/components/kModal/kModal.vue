<template>
  <transition name="fade">
    <div class="overlay" v-if="show" @click="closeModal">
      <div class="modal-w">
        <div class="modal-cnt" :style="{width: width + 'px', height: height + 'px'}" @click.stop>
          <div class="modal-close" title="Закрыть" @click="closeModal"></div>
          <slot></slot>
        </div>
      </div>
    </div>
  </transition>
</template>

<script type="text/javascript">
export default {
  props: {
    height: {
      type: String,
      default: '500'
    },
    visible: Boolean,
    width: {
      type: String,
      default: '900'
    }
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
    closeModal () {
      this.show = false
      this.$emit('close')
    }
  }

}
</script>

<style lang="sass" src="./style.sass">
</style>
