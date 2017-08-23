<template>
  <label :class="['sun-radio']">
    <input type="radio" class="radio" :disabled="disabled"
      :checked="isOption ? value == option : value"
      :value="option"
      @change="changeValue">
    <span class="as-text">
      <slot></slot>
    </span>
  </label>
</template>
<script>
  export default {
    props: {
      value: {
        default: false
      },
      option: {
        default: null
      },
      disabled: ''
    },
    computed: {
      isOption () {
        return this.option !== null
      }
    },
    methods: {
      changeValue (val) {
        this.$emit('input', this.isOption ? this.option : !this.value)
      }
    }
  }
</script>