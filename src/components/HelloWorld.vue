<template>
  <div>
    <button @click="$emit('input', timer())">TEST1</button>{{ /* こっちは上手くいく */}}
    <button @click="timer().then(result => $emit('input2', result))">TEST2</button>{{ /* これだと動くけどエラーが出る… */}}
  </div>
</template>

<script>
export default {
  methods:{
    async timer(){
      return new Promise((resolve)=> {
        setTimeout(()=>{resolve('test')}, 3000)
      })
    }
  }
}
</script>