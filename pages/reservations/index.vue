<template>
  <div class="container is-fluid">
    <section class="section">
      <label class="label">Reservations</label>
      <div class="columns">
        <div class="column 1-half">
          <div class="control is-large">
            <div class="select">
              <select class="select is-info" @change="getReservation($event)">
                <option value="" selected disabled>
                  Select reservation
                </option>
                <option v-for="reservation in reservations" :key="reservation.confirmationCode" :value="reservation.confirmationCode">
                  {{ reservation.city }}
                </optIon>
              </select>
            </div>
          </div>
        </div>
        <div class="column 1-half">
          <nuxt-link :to="`../`">
            <button class="button">
              Home
            </button>
          </nuxt-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script>

export default {
  // middleware: 'test',
  async asyncData ({ $axios }) {
    const response = await $axios.get('/reservations')
    const reservations = response.data.reservations
    return {
      reservations
    }
  },
  methods: {
    getReservation: (context, $axios) => {
      const resId = event.target.options[event.target.options.selectedIndex].value
      console.log(context)
      window.location.href = '/reservations/' + resId
    }
  },
  head: {
    title: 'Prokasa: reservations list'
  }
}
</script>

<style scoped>

</style>
