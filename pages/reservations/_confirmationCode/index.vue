<template>
  <div>
    this is reservation {{ reservation.city }}
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
