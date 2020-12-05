<template>
  <section>
    <Header />
    All fighters
  </section>
</template>

<script>
import Header from '~/components/Header/Header'
export default {
  name: 'Fighters',
  components: { Header }
}
</script>

<style scoped>
  section {
    text-align: center;
  }
</style>
