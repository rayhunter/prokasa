<template>
  <div class="container is-fluid">
    <section class="section">
      <nuxt-child :reservation="reservation" />
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      reservations: [{
        confirmationCode: 'AAAAAA',
        checkInDate: '2020-02-10',
        checkOutDate: '2020-02-14',
        city: 'San Francisco, CA',
        rating: null,
        cityImage:
          'https://cdn.pixabay.com/photo/2013/11/13/21/14/san-francisco-210230_960_720.jpg'
      }, {
        confirmationCode: 'BBBBBB',
        checkInDate: '2020-03-10',
        checkOutDate: '2020-03-14',
        city: 'Los Angeles, CA',
        rating: 3,
        cityImage:
          'https://cdn.pixabay.com/photo/2016/10/25/12/28/los-angeles-1768743_960_720.jpg'
      }, {
        confirmationCode: 'CCCCCC',
        checkInDate: '2020-04-10',
        checkOutDate: '2020-04-14',
        city: 'New York City, NY',
        rating: 5,
        cityImage:
          'https://cdn.pixabay.com/photo/2016/01/19/18/00/city-1150026_960_720.jpg'
      }]
    }
  },
  computed: {
    reservation () {
      return this.reservations.find(r => r.confirmationCode === this.$route.params.confirmationCode)
    }
  }
}
</script>

<style scoped>

</style>
