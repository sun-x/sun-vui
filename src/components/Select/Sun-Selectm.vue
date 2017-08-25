<template>
  <div :class="['sun-selectm']">
    <SunInput class="xs-width"></SunInput>
    <ul v-model="selects" :class="['sun-options', sizes]">
      <li :class="[sizes]" v-for="option in options" @click="selected(option)">{{option.text}}</li>
    </ul>
  </div>
</template>
<script>
  import SunInput from '../Input/Sun-Input.vue'
  export default {
    props: {
      options: '', // 数据来源
      sizes: ''
    },
    components: {
      SunInput
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