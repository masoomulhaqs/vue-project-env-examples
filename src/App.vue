<template>
  <div id="app">
    <h1>{{ env.VUE_APP_TITLE || 'Welcome' }}</h1>
    <p>You are in <strong>{{ env.NODE_ENV }}</strong> environment.</p>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Key</th>
          <th scope="col">Value</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(value, key) in env" :key="key">
          <td>{{ key }}</td>
          <td>{{ value }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'app',
  computed: {
    env() {
      return process.env;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 14px;
}
</style>

<style scoped>
strong {
  color: red;
}
.table {
  text-align: left;
  margin: 2rem auto;
}
th, td {
  padding: .3rem 1rem;
}
</style>
