<template>
  <input :class="['sun-input']"/>
</template>
<script>
  // 并不需要直接包装input
  export default {
    props: {
      sunWidth: 1
    }
  }
</script>