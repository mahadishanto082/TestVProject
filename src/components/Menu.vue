<template>
  <menu class="menu">
    <div class="menu-item">
      <h2>Menu Item 1</h2>
      <p>Description for Menu Item 1</p>
    </div>
    <div class="menu-item">
      <h2>Menu Item 2</h2>
      <p>Description for Menu Item 2</p>
    </div>
    <div class="menu-item">
      <h2>Menu Item 3</h2>
      <p>Description for Menu Item 3</p>
    </div>
    </menu>
</template>

<script>
export default {

}
</script>

<style>
.menu {
  width: 100vw;
  background-color: blue;
  padding: 1rem 0;
  position: fixed;
  top: 610px; /* Adjust this value to the height of your header */
  left: 0;
  z-index: 999;
  height: auto; /* Adjust as needed */
  box-sizing: border-box;
}
</style>