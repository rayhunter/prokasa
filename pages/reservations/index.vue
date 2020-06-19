<template>
  <div class="container is-fluid">
    <section class="section">
      <h1>Reservations</h1>
      <div v-for="reservation in reservations" :key="reservation.confirmationCode">
        <nuxt-link :to="`/reservations/${reservation.confirmationCode}`">
          {{ reservation.city }}
        </nuxt-link>
      </div>
      <nuxt-link :to="`../`">
        <button class="button is-link is-small">
          Home
        </button>
      </nuxt-link>
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
  },
  head: {
    title: 'Prokasa: reservations list'
  }
}
</script>

<style scoped>

</style>
