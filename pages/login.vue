<template>
  <div>
    <input type="text" name="username" id="" v-model="auth.username" placeholder="username">
    <input type="text" name="password" id="" v-model="auth.password" placeholder="password">
    <button @click="userLogin()">Login</button>
  </div>
</template>

<script>
export default {
  data() {
    return{
      auth: {
        username:null,
        password:null,
      }
    }
  },
  methods:{
      async userLogin() {
      try {
        let response = await this.$auth.loginWith('local', { data: this.auth })
        if(response.data.status=200){
          this.$router.push("/admin");
        }else{
          alert(response);
        }
      } catch (err) {
        console.log(err)
        alert("periksa user / password anda ")
      }
    }
  }
}
</script>


