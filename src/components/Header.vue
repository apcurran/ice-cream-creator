<template>
  <header class="header">
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
  padding: 2rem; 
  background-color: lightseagreen;
  display: flex;
  justify-content: center;
  align-items: center;
}

.header__title {
  position: relative;
}

.header__title::before {
  content: url(../assets/ice-cream-cone.svg);
  position: absolute;
  width: 2.5rem;
  height: 2.5rem;
  top: -10%;
  left: -3rem;
}

</style>
