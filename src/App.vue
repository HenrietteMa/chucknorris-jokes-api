<template>
  <div>
    <p>{{joke}}</p>
    <p> - Chuck Norris</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      joke: null,
    }
  },
  mounted() {
    axios
        .get('https://api.chucknorris.io/jokes/random')
        .then(response => this.joke = response.data.value)
        .catch(error => console.log(error.message))
  },
  name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
