<template>
<div class="check-box">
　　　 <div class="wrapper">
        <div class="box">
          <input type="checkbox"/><span>√</span>
        </div>
        <span>牛奶</span>
      </div>
      
      <div class="wrapper">
        <div class="box">
          <input type="checkbox"/><span>√</span>
        </div>
        <span>水</span>
      </div>
</div>
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