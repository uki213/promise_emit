<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld @input="hoge" @input2="fuga" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  methods:{
    hoge(e){
      // test1 送られてくる引数がpromiseなので、こっちでthenを付ける。
      e.then(result => alert(result))
    },
    fuga(e){
      // test2 引数はただの数値なので、そのまま表示。受け側としてはこっちが自然
      alert(e)
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
