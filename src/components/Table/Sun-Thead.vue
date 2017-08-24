<template>
  <table>
    <tr>
      <td v-if="checked">
        <input type="checkbox" v-model="trData.checked">全选
      </td>
      <td @click="sort($index, sunTr)" v-for="(sunTr, $index) in trData" :class="['sun-thead']">
        <span>{{sunTr}}</span>
      </td>
    </tr>
  </table>
</template>
<script>
  export default {
    props: {
      define: false,
      trData: '',
      checked: ''
    },
    data () {
      return {
        sorts: false
      }
    },
    methods: {
      sort ($index, sunTr) {
        this.sorts = !this.sorts
        this.$emit('sort', $index, this.sorts, sunTr)
      }
    }
  }
</script>