<template>
  <div class="container is-fluid">
    <section class="section">
      <nuxt-child :reservation="reservation" />
    </section>
  </div>
</template>

<script>
export default {
  async asyncData ({ $axios, params }) {
    const response = await $axios.get(`/akasa-data/${params.confirmationCode}`)
    const reservation = response.data
    return {
      reservation
    }
  }
}
</script>

<style scoped>

</style>
