<template>
  <section class="container">
  </section>
</template>

<script>

export default {

  components: {
  },
  mounted() {
    const {code} = this.$route.query;
    this.$axios.get(`http://localhost:3000/auth/github?code=${code}`)
      .then((resp) => {
        console.log(resp.data);
      })
      .catch((err) => {
        console.log(err);
      })
  }
}
</script>
