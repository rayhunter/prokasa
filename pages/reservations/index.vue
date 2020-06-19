<template>
  <div class="container is-fluid">
    <section class="section">
      <h1>Reservations</h1>
      <div v-for="reservation in reservations" :key="reservation.confirmationCode">
        <nuxt-link :to="`/reservations/${reservation.confirmationCode}`">
          {{ reservation.city }}
        </nuxt-link>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData ({ $axios }) {
    const response = await $axios.get('/akasa-data')
    const reservations = response.data.reservations
    return {
      reservations
    }
  }
}
</script>

<style scoped>

</style>
