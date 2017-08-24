<template>
  <table>
    <tr v-for="thData in rows">
      <td v-if="checked" @click="checke(thData)">
        <input type="checkbox" v-model="thData.checked">
      </td>
      <td v-for="sunTr in thData">
        <router-link v-if="sunTr.define" :class="['sun-th']" :to="{path : sunTr.to}" >{{sunTr.text}}
          <slot></slot>
        </router-link>
        <span :class="['sun-th']" @click="operate(thData, $index)" v-else-if="sunTr.constructor===Array" v-for="(text, $index) in sunTr">
          {{text}}</span>
        <span v-else :class="['sun-th']">{{sunTr}}</span>
      </td>
    </tr>
    <tr>
      <td v-if="checked">
        <input type="checkbox">全选
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
        this.$emit('checked', checks)
      }
    }
  }
</script>