<template>
  <div id="app">
    <Header />
    <CreateForm v-on:sendIceCream="updateOrder($event)" />
    <Creations :allOrders="allOrders" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import CreateForm from "@/components/CreateForm.vue";
import Creations from "@/components/Creations.vue";

export default {
  name: 'app',
  components: {
    Header,
    CreateForm,
    Creations
  },
  data() {
    return {
      allOrders: [],
    }
  },
  methods: {
    updateOrder(newOrder) {
      this.allOrders.push(newOrder);
    }
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  background-color: #EDF2F7;
}

</style>
