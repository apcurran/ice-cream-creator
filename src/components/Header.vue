<template>
  <header class="header">
    <img src="../assets/ice-cream-cone.svg" alt="Ice cream icon" class="header__icon">
    <h1 class="header__title">Ice Cream Creator</h1>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style>

.header {
  padding: 1rem 0; 
  background-color: lightseagreen;
  display: grid;
  grid-template-columns: 1.4fr 2fr;
  align-items: center;
}

.header__icon {
  width: 8rem;
  margin-left: 1.5rem;
}

</style>
