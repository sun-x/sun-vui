<template>
<div class="check-box">
　　　 <div class="wrapper">
        <div class="box">
          <input type="checkbox" checked="checked" id="milk" /><span>√</span>
        </div>
        <lable for="milk">牛奶</lable>
      </div>
      
      <div class="wrapper">
        <div class="box">
          <input type="checkbox"  id="water" /><span>√</span>
        </div>
        <label for="water">水</label>
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