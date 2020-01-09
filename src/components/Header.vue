<template>
  <header class="header">
    <img src="../assets/ice-cream.svg" alt="Ice cream icon" class="header__icon">
    <h1 class="header__title">Ice Cream Creator</h1>
    <h3 class="header__attribution">Icon made by <a href="https://www.flaticon.com/authors/freepik" title="Freepik">Freepik</a></h3>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style>

.header {
  padding: 2rem 5rem; 
  background-color: lightseagreen;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header__icon {
  width: 10rem;
}

.header__attribution,
.header__attribution a {
  color: hsl(0, 0%, 80%);
  font-size: .9rem;
}

</style>
