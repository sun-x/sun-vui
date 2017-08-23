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
  </div>
</template>
<script>
import SunBtn from './Btn/Sun-Btn'
import SunInput from './Input/Sun-Input'
import SunRadio from './Radio/Sun-Radio'
export default {
  name: 'hello',
  components: {
    SunBtn,
    SunInput,
    SunRadio
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      optionRadio: {text: 'PHP', value: '1'},
      option: [
        {text: 'PHP', value: '1'},
        {text: 'JS', value: '2'},
        {text: 'JAVA', value: '3'}
      ]
    }
  },
  methods: {
    clickBtn () {
      console.log("i'm a buttom")
    }
  }
}
</script>
