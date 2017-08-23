<template>
  <router-link v-if="to" :class="['sun-btn', type, sizes]" :to="to" >
    <slot></slot>
  </router-link>
  <button v-else :class="['sun-btn', type, sizes]" @click="sunClick">
    <slot></slot>
  </button>
</template>
<script>
export default {
  props: {
    to: '',
    type: '',
    sizes: '',
    disabled: ''
  },
  methods: {
    sunClick ($event) {
      this.$emit('click', $event)
    }
  }
}
</script>
