

<template>
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
<script src="script.js"></script>
<style scoped>
a {
  color: #42b983;
}
</style>
