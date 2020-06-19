<template>
  <div>
    <p>this is reservation {{ reservation.city }}</p>
    <dl>
      <dt>Dates</dt>
      <dd>{{ reservation.checkInDate }} - {{ reservation.checkOutDate }}</dd>
      <dt>Confirmation#</dt>
      <dd>{{ reservation.confirmationCode }}</dd>
      <dt>Rating</dt>
      <dd>{{ reservation.rating }}</dd>
    </dl>
    <img :src="reservation.cityImage"></img>
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

</style>
