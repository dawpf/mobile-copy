<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />

    <div>
      <button @click="btnClick">点击复制到剪切板</button>
    </div>

    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods: {
    btnClick() {
      let tag = document.createElement('input')
      tag.setAttribute('id', 'copy_input')
      tag.value = 'test111' // 要复制到剪切板的内容
      document.getElementsByTagName('body')[0].appendChild(tag)
      document.getElementById('copy_input').select()
      document.execCommand('copy')
      document.getElementById('copy_input').remove()

      alert('链接已复制到剪切板')
    }
  }
}
</script>
