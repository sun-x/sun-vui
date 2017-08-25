<template>
  <div class="hello">
    <div>按钮组-type</div>
    <SunBtn type="is-danger">danger</SunBtn>
    <SunBtn type="is-success">success</SunBtn>
    <SunBtn sizes="xs">default</SunBtn>
    <SunBtn type="is-info">info</SunBtn>
    <SunBtn type="is-warn">warn</SunBtn>
    <div>按钮组-sizes</div>
    <SunBtn type="is-info">info</SunBtn>
    <SunBtn type="is-danger" sizes="md">danger</SunBtn>
    <SunBtn type="is-success" @click="clickBtn">success</SunBtn>
    <SunBtn  to="/" @click="clickBtn">to</SunBtn>
    <div>输入框</div>
    <SunInput class="xs"></SunInput>
    <div>单选框</div>
    <SunRadio option="optionRadio"></SunRadio>
    <div>多选框</div>
    <SunCheckbox option="optionRadio"></SunCheckbox>
    <div>表格</div>
    <SunTable @operate="operate" @checked="checked" :rows="thData" :columns="trDatas" :all-check="true"></SunTable>
    <div>下拉单选</div>
    <SunSelect :options="option" @selected="select(selected)"></SunSelect>
    <SunSelectM :options="option" sizes="xs"></SunSelectM>
  </div>
</template>
<script>
import SunBtn from './Btn/Sun-Btn'
import SunInput from './Input/Sun-Input'
import SunRadio from './Radio/Sun-Radio'
import SunCheckbox from './Checkbox/Sun-Checkbox'
import SunTbody from './Table/Sun-Tbody'
import SunThead from './Table/Sun-Thead'
import SunTable from './Table/Sun-Table'
import SunSelect from './Select/Sun-Select'
import SunSelectM from './Select/Sun-SelectM'
export default {
  name: 'hello',
  components: {
    SunBtn,
    SunInput,
    SunRadio,
    SunCheckbox,
    SunThead,
    SunTbody,
    SunTable,
    SunSelect,
    SunSelectM
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      optionRadio: {text: 'PHP', value: '1'},
      selected: 3,
      option: [
        {text: 'PHP', value: '1'},
        {text: 'JS', value: '2'},
        {text: 'JAVA', value: '3'}
      ],
      trDatas: [
        'PHP',
        'JAVA',
        'JS',
        'PYTHON',
        'GO',
        '.NET',
        'RUBY',
        '操作'
      ],
      thData: [
        {
          'PHP': 1,
          'JAVA': 2,
          'JS': 3,
          'RUBY': 7,
          'PYTHON': 4,
          'GO': 5,
          '.NET': 4,
          '操作': ['删除', '编辑', '增加']
        },
        {
          'PHP': 2,
          'JAVA': 3,
          'JS': 3,
          'RUBY': 7,
          'PYTHON': 4,
          'GO': 54,
          '.NET': 6,
          '操作': ['删除', '编辑', '增加']
        },
        {
          'PHP': 3,
          'JAVA': 1,
          'JS': 3,
          'RUBY': 71,
          'PYTHON': 2,
          'GO': 5,
          '.NET': 6,
          '操作': ['删除', '编辑', '增加']
        },
        {
          'PHP': 4,
          'JAVA': 0,
          'JS': 10,
          'RUBY': 7,
          'PYTHON': 6,
          'GO': 5,
          '.NET': 61,
          '操作': ['删除', '编辑', '增加']
        }
      ]
    }
  },
  methods: {
    clickBtn () {
      console.log("i'm a buttom")
    },
    operate (entry, $index) {
      console.log(entry, $index)
    },
    checked (checkedData) {
      console.log(checkedData)
    },
    select (selected) {
      console.log(selected)
    }
  }
}
</script>
