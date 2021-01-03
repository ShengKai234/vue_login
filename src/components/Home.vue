<template>
  <div class="hello">
    <img src="../assets/killua.jpg">
    <h1>{{ msg }}</h1>
    <button class="btn btn-danger btn-rounded" v-on:click="login">Sign in!</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      msg: 'Welcome to My Vue App'
    }
  },
  methods: {
    login: function () {
      this.$router.push({path: '/Login'})
    }
  }
}
</script>
