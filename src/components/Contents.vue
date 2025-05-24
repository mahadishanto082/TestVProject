<template>
  <div class="contents">
    <ul class="links">
      <li>
        <a href="#home">
          <img
            src="../assets/OIP.jpg"
            alt="Logo"
            style="height: 50px; border-radius: 50%"
          />
          Shipping over $49.99
        </a>
      </li>
      <li>
        <a href="#about">
          <img
            src="../assets/R.png"
            alt="Logo"
            style="height: 50px; border-radius: 50%"
          />ZillaCash: $5 for every $100</a
        >
      </li>
      <li>
        <a href="#services">
          <img
            src="../assets/OIP (1).jpg"
            alt="Logo"
            style="height: 50px; border-radius: 50%"
          />Customer Service From Riders</a
        >
      </li>
    </ul>
    <img
      src="../assets/banner.jpeg"
      alt="Logo"
      style="
        width: 100%;
        justify-content: center;
        display: block;
        margin: 0 auto;
      "
      @click="nextPage"
    />
    <h1 style="text-align: center; margin-top: 2rem">
      Hottest Brands On Sale
    </h1>
    <div class="brands">
      <span class="arrow" @click="slideLeft">&#8249;</span>

      <!-- ‹ -->
      <ul class="brands">
      <li v-for="(brand, index) in visibleBrands" :key="index">{{ brand }}</li>
    </ul>

      

        <span class="arrow" @click="slideRight">&#8250;</span> <!-- › -->

    </div>
    </div>
    

</template>

<script>
import { ref, computed } from 'vue';

export default {
  name: brands,
  setup(){
    const brands =ref([
      "Brand A",
      "Brand B",
      "Brand C",
      "Brand D",
      "Brand E",
      // Number of brands to show at a time

      
    ])
    const currentIndex = ref(0);
    const itemsToShow = 3; // Number of brands to show at a time
    const visibleBrands = computed(() => {
      return brands.value.slice(currentIndex.value, currentIndex.value + itemsToShow);
    });
    const slideLeft =()=>{
      if (currentIndex.value > 0) {
        currentIndex.value -= itemsToShow;
      };
    };
    const slideRight = () => {
      if (currentIndex.value + itemsToShow < brands.value.length) {
        currentIndex.value += itemsToShow;
      }
    };

    const nextPage = () => {
      alert("Navigating to the next page!"); // Placeholder action

    }

  }
};
</script>

<style>
.contents {
  width: 100%;
  height: 100%;
  display: block;
  cursor: pointer;
  position: relative;
  bottom:35rem; /* show pointer on hover */
  /* show pointer on hover */
}

.links {
  display: flex;
  justify-content: center;
  gap: 2rem;
  font-size: 1.5rem;
  position: relative;
  bottom: 2rem; /* show pointer on hover */
  list-style: none;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  color: black;
}
.contents::-webkit-scrollbar {
  width: 8px;
}

.contents::-webkit-scrollbar-thumb {
  background-color: rgba(0,0,0,0.3);
  border-radius: 4px;
}
.brands {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
}
.brand-list {
  horizontal-align: center;
  display: flex;
  justify-content: center;
  gap: 2rem;
  font-size: 1.5rem;
  list-style: none;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  color: black;
}

</style>
