<template>
  <menu class="menu">
    <ul>
      <li><a href="#home">Helmet </a></li>
      <li><a href="#about">Riding Gear</a></li>
      <li><a href="#services">Parts</a></li>
      <li><a href="#contact">Accecories</a></li>
      <li><a href="#contact">Tires</a></li>
      <li><a href="#contact">2025 GUIDES</a></li>
      <li><a href="#contact" style="color: red">Sales</a></li>
      <li>
        <a href="#contact">
          <img
            src="../assets/blog.png"
            alt="Logo"
            style="
              height: 50px;
              border-radius: 50%;
              position: relative;
              right: -10rem;
            "
          />
        </a>
      </li>
    </ul>
    <div class="hamburger-menu">
      <div class="menu-icon" @click="toggleMenu">
        &#9776; <span class="menu-text">MENU</span>
      </div>
      <ul v-if="isMenuOpen" class="dropdown-menu">
        <li class="title">
          <img class="cancel-icon" @click="closeMenu" 
            src="../assets/close-button.png"
            alt="logo"
            style="height: 50px; border-radius: 50%"
          />Menu
        </li>
        <li><a href="#home">Helmet </a></li>
        <li><a href="#about">Riding Gear</a></li>
        <li><a href="#services">Parts</a></li>
        <li><a href="#contact">Accecories</a></li>
        <li><a href="#contact">Tires</a></li>
        <li><a href="#contact">2025 GUIDES</a></li>
        <li><a href="#contact" style="color: red">Sales</a></li>
      </ul>
    </div>
    <hr class="section-break" />
    
    

   
  </menu>
</template>

<script>
export default {
  name: "Menu",
  methods: {
    nextPage() {
      // Logic to navigate to the next page
      alert("Navigating to the next page!"); // Placeholder action
    },
  },
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
      const menuIcon = document.querySelector(".menu-icon");
      if (this.isMenuOpen) {
        menuIcon.style.transform = "rotate(1deg)";
      } else {
        menuIcon.style.transform = "rotate(0deg)";
      }
      
    },
    closeMenu() {
      this.isMenuOpen = false;
      const menuIcon = document.querySelector(".menu-icon");
      menuIcon.style.transform = "rotate(0deg)";
  }
    },
  };
</script>

<style>

.section-break {
  border: none;
  height: 5px;
  background-color: red; /* Or any color */
  margin: 2rem 0; /* Top and bottom spacing */
}

.menu {
  width: 100%;
  background-color:white;
  padding: 1rem 0;
  position: fixed;
  margin-top: 50px; /* Adjusted to be above the footer */
  top: 80px;
  left: 0;
  
  height: 10%;
  box-sizing: border-box;
}

.menu ul {
  display: flex;
  flex-wrap: wrap; /* wrap on smaller screens */
  justify-content: center;
  gap: 1rem;
  font-size: 1.5rem; /* reduced from 2rem */
  list-style: none;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  color: black;
}

.menu-icon {
  cursor: pointer;
  font-size: 2.5rem; /* smaller icon */
  user-select: none;
  color: black;
  
  position: relative;
  top: -2rem;
  left: 6rem;
  align-items: center;
}

/* Show hamburger on small screens */
@media (max-width: 768px) {
  .menu ul {
    display: none; /* hide horizontal menu */
  }
  .menu-icon {
    display: flex;
  }
  .dropdown-menu {
    left: 1rem; /* reduce offset */
    width: calc(100% - 2rem); /* responsive width */
    max-width: 300px;
  }
  .title {
    font-size: 1.5rem;
  }
  .section-break {
    margin: 1rem 0;
  }
}

@media (max-width: 480px) {
  .menu-icon {
    font-size: 2rem;
    left: 1rem;
  }
  .dropdown-menu {
    width: 100%;
    left: 0;
  }
  .menu ul {
    font-size: 1.2rem;
  }
}
.dropdown-menu {
  display: flex; /* Horizontal layout */
  flex-direction: column; /* Items in a row */
  list-style: none;
  position: relative;
  left: 6rem;
  gap: 1rem;
  padding: 0.5rem 1rem;
  width: 20rem; /* Adjust width as needed */
  background-color: white;
  border: 2px solid #ccc;
  margin-top: 0.5rem;
}

.dropdown-menu li {
  padding: 0.25rem 0.5rem;
  width: 20rem;
}
.title {
  font-size: 2rem;
  font-weight: bold;
  color: white;

  background-color: black;
}
.cancel-icon {
  cursor: pointer;
  font-size: 3rem;
  user-select: none;
  color: black;
  display: flex;
  position: relative;
  top: 2rem;
  left: 6rem;
  align-items: center;
}
</style>
