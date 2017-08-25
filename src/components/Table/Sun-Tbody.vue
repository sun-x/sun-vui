<template>
  <table>
    <tr v-for="thData in rows">
      <td v-if="checked" @click="checke(thData)">
        <input type="checkbox" v-model="thData.checked">
      </td>
      <td v-for="sunTr in thData">
        <!-- 页面跳转 -->
        <router-link v-if="sunTr.define" :class="['sun-th']" :to="{path : sunTr.to}" >{{sunTr.text}}
          <slot></slot>
        </router-link>
        <!-- 数据渲染 -->
        <span :class="['sun-th']" @click="operate(thData, $index)" v-else-if="sunTr.constructor===Array" v-for="(text, $index) in sunTr">
          {{text}}</span>
        <span v-else :class="['sun-th']">{{sunTr}}</span>
        <!-- 自定义操作 -->
      </td>
    </tr>
    <tr>
      <td v-if="checked">
        <input type="checkbox" v-model="rows.checked" @click="checkedAll(rows)">全选
      </td>
    </tr>
  </table>
</template>
<script>
  export default {
    props: {
      define: false,
      rows: '',
      checked: ''
    },
    methods: {
      operate (entry, $index) {
        this.$emit('operate', entry, $index)
      },
      checke (checks) {
        this.$emit('checked', this.rows.filter((item) => {
          return item.checked
        }))
      },
      checkedAll (checkData) {
        this.rows.forEach((element, index) => {
          console.log(element.checked)
          element.checked = true
          console.log(element.checked)
          this.$set(this.rows, index, this.rows[index])
        })
        this.$emit('checkAll', checkData)
      }
    }
  }
</script>