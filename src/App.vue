<template>
    <div id="app">
      <Header />
      <Nav />
      <Menu />
      
      
      <main>

        <h1>Welcome to the Motorcycle Store</h1>
        
        
      </main>
      <Contents />
    </div>
  </template>
  
  <script>
  import Header from './components/Header.vue';
  import Nav from './components/Nav.vue';
  import Menu from './components/Menu.vue';
  import Contents from "./components/Contents.vue"
  
  
  export default {
    name: 'App',
   
    components: {
      Header,
      Nav,
      Menu,
      Contents,
     
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
  flex-grow: 1;        /* so main stretches to fill available space */
  min-height: 300px;
  height: 100vh;       /* full viewport height */
  overflow-y: auto;    /* enable vertical scrolling */
  box-sizing: border-box; 
  }
  </style>
  