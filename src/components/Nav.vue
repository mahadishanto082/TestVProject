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

.navbar {
  width: 100%;
  background-color: black;
  padding: 1rem 1rem; /* reduce side padding */
  position: fixed;
  top: 60px;
  left: 0;
  z-index: 999;
  min-height: 70px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  box-sizing: border-box;
}

.navbar ul {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin: 0;
  padding: 0;
  list-style: none;
  justify-content: center;
  width: 100%;
}

.logo {
  position: relative;
  right: 0;
  margin-right: auto;
}

.search-box {
  padding: 0.4rem 1rem; /* smaller padding */
  font-size: 1rem;
  border: none;
  border-radius: 4px;
  flex-grow: 1; /* let search box grow on larger screens */
  max-width: 300px;
  min-width: 150px;
}

@media (max-width: 768px) {
  .navbar ul {
    justify-content: center;
  }
  .btn1 {
    font-size: 0.9rem;
    padding: 0.4rem 1rem;
  }
  .search-box {
    max-width: 100%;
    padding: 0.4rem 0.8rem;
  }
  .logo img {
    height: 40px;
  }
}

@media (max-width: 480px) {
  .navbar ul {
    flex-direction: column;
    gap: 0.5rem;
    align-items: center;
  }
  .btn1 {
    width: 100%;
  }
  .search-box {
    width: 100%;
    margin-bottom: 0.5rem;
  }
  .logo img {
    height: 35px;
  }
}

</style>
