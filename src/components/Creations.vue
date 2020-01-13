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

.main {
  margin: 3rem auto;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  grid-gap: 2rem;
  width: 60rem;
  max-width: 92.5%;
}

.created-order {
  position: relative;
  padding: 3rem 1.5rem;
  box-shadow: 0 5px 12px rgba(0, 0, 0, .25);
  border-radius: 10px;
  background-color: #fff;
}

.created-order__list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  list-style: none;
}

.created-order__item {
  margin: .5rem .2rem;
  padding: .35rem .9rem;
  border-radius: 500px;
  background-color: #cbd5e0;
}

.created-order__delete {
  background: url(../assets/icon-trash.svg) no-repeat center center;
  padding: 1rem;
  cursor: pointer;
  border: none;
  position: absolute;
  bottom: 7px;
  left: 7px;
  opacity: .55;
  outline: none;
}

.created-order__delete:hover,
.created-order__delete:focus {
  opacity: 1;
}

</style>