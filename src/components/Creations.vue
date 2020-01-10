<template>
  <main class="main">
      <article v-for="(order, index) in allOrders" :key="index" class="created-order">
        {{ order }}
      </article>
  </main>
</template>

<script>
export default {
    name: "Creations",
    props: ["allOrders"],
    data() {
      return {
      
      }
    }
}
</script>

<style>

</style>