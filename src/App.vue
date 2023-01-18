<template>
  <div id="app">
    <ButtonForm msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import ButtonForm from './components/ButtonForm.vue'

export default {
  name: 'App',
  components: {
    ButtonForm
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: linear-gradient(-128deg, rgba(255, 181, 32, 0.93) 3%, rgba(239, 39, 153, 0.93) 88%, rgba(237, 18, 171, 0.93) 100%);
  display: flex;
  width: 100%;
  height: 100vh;
  justify-content: center;
  align-items: center;
}

input {
  border:none;
  outline: 1px rgb(221, 220, 220) solid;
  border-radius: 5px;
  height: 29px;
  padding: 2px 5px;
  margin-top: 5px;
}
textarea {
  border:none;
  outline: 1px rgb(221, 220, 220) solid;
  border-radius: 5px;
}
</style>
