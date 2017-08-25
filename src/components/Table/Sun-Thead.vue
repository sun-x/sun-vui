<template>
  <table>
    <tr>
      <td v-if="checked">
        <input type="checkbox" v-model="trData.checked" @click="checkedAll(trData)">全选
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
      checked: '' // 是否有选项
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
      },
      checkedAll (checkData) {
        this.$emit('checkAll', checkData)
      }
    }
  }
</script>