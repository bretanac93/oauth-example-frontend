<template>
  <section class="container">
    <a href="https://github.com/login/oauth/authorize?scope=user:email&client_id=356b757559647d2a3fba">Login with Github</a>
  </section>
</template>

<script>

export default {
  components: {
  },
  mounted() {
    const {code} = this.$route.query; // Retrieve the code provided by the OAuth provider
    if (code) {
      this.$axios.get(`http://localhost:3000/auth/github?code=${code}`) // Send it to your server
      .then((resp) => {
        console.log(resp.data); // Check your console :)
      })
      .catch((err) => {
        console.log(err);
      })
    }
  }
}
</script>
