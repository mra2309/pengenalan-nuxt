<template>
  <div>
    Sudah Login
    {{this.$auth.user}}
    <button @click="$auth.logout()">Logout</button>
  </div>
</template>

<script>
export default {
  auth:true,
}
</script>
