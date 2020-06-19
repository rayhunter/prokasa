<template>
  <div>
    <div class="container">
      <div class="columns notification">
        <div class="column">
          Reservation for: {{ reservation.city }}
        </div>
        <div class="column is-narrow">
          <nuxt-link :to="`../reservations/`">
            <button class="button is-link is-small">
              Search All Reservations
            </button>
          </nuxt-link>
        </div>
      </div>
      <div class="columns">
        <div class="column">
          <dl>
            <dt>Dates</dt>
            <dd>{{ reservation.checkInDate }} - {{ reservation.checkOutDate }}</dd>
            <hr>
            <dt>Confirmation#</dt>
            <dd>{{ reservation.confirmationCode }}</dd>
            <hr>
            <dt>Rating</dt>
            <dd>{{ reservation.rating }}</dd>
            <hr>
          </dl>
        </div>
        <div class="column">
          <img :src="reservation.cityImage"></img>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    reservation: {
      type: Object,
      default: () => {
        return { city: 'Boston' }
      }
    }
  }
}
</script>

<style scoped>
.columns {
  padding-left: 20px;
}
.column {
  padding-right: 0;
}
.notification a:not(.button):not(.dropdown-item) {
  text-decoration: none;
}
</style>
