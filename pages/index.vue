<template>
  <div class="container is-fluid">
    <section class="section my-theme">
      <h1 class="prokasa title">
        prokasa
      </h1>
      <h2 class="subtitle">
        an application that renders Kasa reservation data to a user
      </h2>
      <nuxt-link :to="`./reservations/`">
        <button class="button is-link">
          Search Reservations
        </button>
      </nuxt-link>
    </section>
  </div>
</template>

<script>
export default {
  components: {
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.my-theme {
  background-color: #421c52;
}
.prokasa {
  color: white;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: white;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
