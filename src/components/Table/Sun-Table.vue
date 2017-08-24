<template>
  <div class="sun-table">
    <SunThead define="" :trData="columns" @sort="sort" :checked="allCheck"></SunThead>
    <SunTbody @operate="operate" define="" :rows="rows" :checked="allCheck" @checked="checked"></SunTbody>
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
    rows: '',
    allCheck: false
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
    checked (checkedData) {
      this.$emit('checked', checkedData)
    }
  }
}
</script>
