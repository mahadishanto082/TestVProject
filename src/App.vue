<template>
    <div id="app">
      <Header />
      <Nav />
      <Menu />
      <main>
        <h1>Welcome to My Vue App</h1>
      </main>
    </div>
  </template>
  
  <script>
  import Header from './components/Header.vue';
  import Nav from './components/Nav.vue';
  import Menu from './components/Menu.vue';
  
  export default {
    name: 'App',
   
    components: {
      Header,
      Nav,
      Menu,
    },
  };
  </script>
  
  <style>
  body {
    margin: 0;
    font-family: Avenir, Helvetica, Arial, sans-serif;
  }
  #app {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
  main {
    padding: 2rem;
  }
  </style>
  