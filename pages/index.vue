<template>
  <div class="container">
    <Header />
    <Carousel />
  </div>
</template>

<script>
import Header from '~/components/Header/Header'
import Carousel from '~/components/Cards/Carousel'
export default {
  components: { Carousel, Header }
}
</script>

<style>
.xxx {
  color: red;
}
</style>
