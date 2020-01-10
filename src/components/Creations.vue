<template>
  <main class="main">
      <article v-for="(order, index) in allOrders" :key="index" class="created-order">
        <ul class="created-order__list">
          <li class="created-order__item">{{ order.container }}</li>
          <li v-for="(flavor, index) in order.flavors" :key="index" class="created-order__item">{{ flavor }}</li>
          <li v-for="(topping, index) in order.toppings" :key="index" class="created-order__item">{{ topping }}</li>
        </ul>
        <button @click="removeOrder(order)" class="created-order__delete"></button>
      </article>
  </main>
</template>

<script>
export default {
    name: "Creations",
    props: ["allOrders"],
    data() {
      return {
        removeOrder(order) {
          const orderIndex = this.allOrders.indexOf(order);
          this.allOrders.splice(orderIndex, 1);
        }
      }
    }
}
</script>

<style>

.created-order {
  margin: 2rem;
  padding: 2rem;
  color: #fff;
  background-color: #222;
}

.created-order__delete {
  background: url(../assets/icon-trash.svg) no-repeat center center;
  padding: 1rem;
  cursor: pointer;
}

</style>