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
  background: linear-gradient(to right, #1488cc, #2b32b2);
  color: #fff;
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
  top: 0;
  left: -3rem;
}

</style>
