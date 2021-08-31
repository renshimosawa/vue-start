<script setup>
import { ref } from 'vue'
// import Culcurate from './culcurateScript

defineProps({
  msg: String
})

const count = ref(0)

var app = new Vue({ 
  el: '#app',
  data: {
      output: '0',
      items: [
          ['7', '8', '9', '/'],
          ['4', '5', '6', '*'],
          ['1', '2', '3', '-'],
          ['0', '.', '+', '=']
      ]
  },
  methods: {
      calc: function (cmd) {
          if(cmd === '='){
              this.output = eval(this.output)
          }else if(cmd === 'C'){
              this.output = '0'
          }else if(this.output === '0') {
              this.output = cmd
          }else{
              this.output += cmd
          }
      }
  }
});

</script>

<template>
  <!-- <h1>{{ msg }}</h1> -->

  <!-- <p>
    Recommended IDE setup:
    <a href="https://code.visualstudio.com/" target="_blank">VSCode</a>
    +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
  </p>

  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p> -->

  <!-- <button type="button" @click="count++">count is: {{ count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p> -->
   <table id="app">
            <tr>
                <td colspan="3"><input type="text" v-model="output"></td>
                <td><button value="C" v-on:click="calc('C')">C</button></td>
            </tr>
              <!-- <tr v-for="row in items"> -->
            <tr>
              <!-- <td v-for="item in row"> -->
              <td>
                <button v-on:click="calc(item)">{{ item }}</button>
              </td>
            </tr>
    </table>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
