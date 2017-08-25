<template>
  <div>
    <select v-model="selects" @change="selected(selects)">
      <option v-for="option in options" :value="option.value">
        {{ option.text }}
      </option>
    </select>
  </div>
</template>
<script>
  export default {
    props: {
      options: '' // 数据来源
    },
    data () {
      return {
        selects: ''
      }
    },
    computed: {
    },
    mounted () {
      this.selected()
    },
    methods: {
      selected (selecteds) {
        this.$emit('selected', selecteds)
      }
    }
  }
</script>