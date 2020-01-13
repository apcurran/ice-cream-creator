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
  background-color: #EDF2F7;
}

body,
button,
input {
  font-family: 'Poppins', sans-serif;
  letter-spacing: .02em;
}

</style>
