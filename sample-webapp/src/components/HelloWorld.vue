<template>
  <div class="hello">
    <h1>This application is Sample WebApp for CICD lesson(version1.0.1).</h1>
    <div>Response from REST API is... {{ info }}</div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      info: null
    }
  }
  ,
  mounted() {
    const BACKEND_URL = 'https://hmntmy.f5.si/api'
    axios
      .get(BACKEND_URL)
      .then(response => (this.info = response.data))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
