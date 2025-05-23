<template>
  <nav class="navbar">
    <ul>
      <li><a href="#" class="logo">
        <img src="../assets/trademark.png" alt="Logo" style=" height: 50px; border-radius: 50%; margin-right: 10px; position:relative ; bottom:10px " >
      </a></li>
      <li>
        <button class="btn1" @click="handleShopClick">SHOP YOUR RIDE</button>
      </li>
      <input type="search" class="search-box" placeholder="Search..." />
      <li><a href="#">
        <img src="../assets/membership.png" alt="Logo" style=" height: 50px; border-radius: 50%; margin-right: 10px; position:relative ; bottom:10px " >
      </a></li>
      <li><a href="#">
        <img src="../assets/OIP (7).jpg" alt="Logo" style="width: 50px; height: 50px; border-radius: 50%; margin-right: 10px; position:relative ; bottom:10px " >
      </a></li>
      <li><a href="#">
        <img src="../assets/OIP (8).jpg" alt="Logo" style="width: 50px; height: 50px; border-radius: 50%; margin-right: 10px; position:relative ; bottom:10px " >
      </a></li>
      
    </ul>
    
    
  </nav>
</template>
<script >
export default{
    methods: {
        handleShopClick() {
        alert('Button clicked!');
      },
    },
}
</script>

<style scoped>
.navbar {
  width: 100vw;
  background-color:black;
  padding: 1rem 2rem;
  position: fixed;
  top: 60px;
  left: 0;
  z-index: 999;
  margin: 0;
  box-sizing: border-box;
  height: 70px;

  display: flex;
  justify-content: center;  /* Center all items horizontally */
  align-items: center;
  gap: 2rem; /* spacing if you have multiple items */
}
.navbar ul {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

.logo{
  position:relative;
  right: 10rem;
}
.btn1 {
  padding: 0.5rem 1.5rem;
  background-color: orangered;
  color: white;
  font-weight: bold;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.btn1:hover {
  background-color: #0056b3;
}

.navbar btn1 {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

.navbar a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}


.navbar ul {
  display: flex;
  gap: rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

.navbar a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.search-box {
  padding: 0.4rem 10rem ;
 
  font-size: 1rem;
  border: none;
  border-radius: 4px;
}

</style>
