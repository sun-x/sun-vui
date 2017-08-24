<template>
    <div class="sex">
        <span class="radio_btn">
            <input type="radio" name="sex" id="man" />
            <span></span>
        </span>
        <label for="man" >男</label>

        <span class="radio_btn">
            <input type="radio" name="sex" id="male">
            <span></span>
        </span>
        <label for="male">女</label>
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