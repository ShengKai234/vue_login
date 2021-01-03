<template>
    <div class="container col-md-4 mb-4">
        <br>
        <!-- Card -->
        <div class="card">
            <!-- Card body -->
            <div class="card-body">
                <!-- Material form login -->
                <form>
                    <p class="h4 text-center mb-4">Sign up</p>
                    <label for="defaultFormRegisterNameEx" class="grey-text">Your name</label>
                    <input type="text" id="defaultFormRegisterNameEx" class="form-control"/>
                    <br/>
                    <label for="defaultFormRegisterPasswordEx" class="grey-text">Your password</label>
                    <input type="password" id="defaultFormRegisterPasswordEx" class="form-control"/>
                    <div class="text-center mt-4">
                    <button class="btn btn-unique" type="submit">Sign In</button>
                    </div>
                </form>
                <!-- Material form login -->
            </div>
            <!-- Card body -->
        </div>
        <!-- Card -->
    </div>
</template>
<script>
import Cookies from 'js-cookie'

export default {
  data () {
    return {
      loginForm: {
        username: '',
        password: '',
        token: ''
      }
    }
  },
  methods: {
    handleLogin () {
      const token = 'asdsadsafASFadfsaf'
      let username = this.loginForm.username
      let password = this.loginForm.password
      if (username !== '' && password !== '') {
        this.loginForm.token = token
      } else {
        alert('帳號密碼不能為空')
      }
      Cookies.set('login', JSON.stringify(this.loginForm), { expires: 1 })
      console.log(this.loginForm)
      if (Cookies.get('login') && this.loginForm.token) {
        this.$router.push({name: 'Dashboard'})
      }
    },
    removeCookie () {
      Cookies.remove('login')
    }
  }
}
</script>
