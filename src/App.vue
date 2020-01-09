<template>
  <div id="app">
    <Header />
    <CreateForm />
    <Creations />
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
}

</style>
