<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <form>
      <a href="javascript:;" @click="showStu">showStu</a>
      <p>{{ testData }}</p>
    </form>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      testData : ''
    }
  },
  methods: {
    showStu() {
      this.$http.get('/api/Stu/showStu')
        .then( (res) => {
          console.log('res', res);
          this.testData = res.bodyText;
        })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
