<template>
  <div class="sun-table">
    <SunThead define="" :trData="columns" @sort="sort" :checked="checked" @checkAll="checkAll"></SunThead>
    <SunTbody @operate="operate" define="" :rows="rows" :checked="checked" @checked="checked" @checkAll="checkAll"></SunTbody>
  </div>
</template>
<script>
import SunTbody from './Sun-Tbody'
import SunThead from './Sun-Thead'
export default {
  name: 'sun-table',
  components: {
    SunThead,
    SunTbody
  },
  props: {
    columns: '',
    rows: ''
  },
  methods: {
    operate (entrys, $index) {
      if (entrys.constructor === Object) {
        return this.$emit('operate', entrys, $index)
      }
      let entry = []
      entrys.forEach(element => {
        entry.push(element.text)
      }, this)
      this.$emit('operate', entry, $index)
    },
    sort ($index, sorts, sunTr) {
      this.rows.sort((first, second) => {
        if (!sorts) {
          return first[sunTr] < second[sunTr]
        } else {
          return first[sunTr] > second[sunTr]
        }
      })
    },
    forEachs (data) {
      data.forEach((element, index) => {
        this.$set(this.rows, index, this.rows[index])
      })
    },
    checked (checkedData) {
      // checkedData.forEach((item, index) => {
      //   this.$set(this.rows, index, this.rows[index])
      // })
      // this.rows.forEach((element, index) => {
      //   this.$set(this.rows, index, this.rows[index])
      // })
      this.forEachs(checkedData)
      this.forEachs(this.rows)
      this.$emit('checked', checkedData)
    },
    checkAll (checkData) {
      this.rows.forEach((element, index) => {
        element.checked = checkData.checked
        this.$set(this.rows, index, this.rows[index])
      })
    }
  }
}
</script>
