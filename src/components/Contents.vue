<template>
  <div class="contents">
    <ul class="links">
      <li>
        <a href="#home">
          <img src="../assets/OIP.jpg" alt="Logo" style="height: 50px; border-radius: 50%" />
          Shipping over $49.99
        </a>
      </li>
      <li>
        <a href="#about">
          <img src="../assets/R.png" alt="Logo" style="height: 50px; border-radius: 50%" />
          ZillaCash: $5 for every $100
        </a>
      </li>
      <li>
        <a href="#services">
          <img src="../assets/OIP (1).jpg" alt="Logo" style="height: 50px; border-radius: 50%" />
          Customer Service From Riders
        </a>
      </li>
    </ul>

    <img
      src="../assets/banner.jpeg"
      alt="Logo"
      style="width: 100%; justify-content: center; display: block; margin: 0 auto"
      @click="nextPage"
    />

    <h1 style="text-align: center; margin-top: 2rem">Hottest Brands On Sale</h1>

    <div class="brands-container">
      <span class="Arrow" @click="slideLeft">&#8249;</span>
      <ul class="brand-list" :class="{ sliding: isSliding }">
        <li v-for="(brand, index) in visibleBrands" :key="index" class="brand-item">
          <a :href="'#brand-' + index">{{ brand }}</a>
        </li>
      </ul>
      <span class="Arrow" @click="slideRight">&#8250;</span>
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue';

export default {
  name: 'Brands',
  setup() {
    const brands = ref([
      "Brand A",
      "Brand B",
      "Brand C",
      "Brand D",
      "Brand E",
      "Brand F",
      "Brand G"
    ]);

    const currentIndex = ref(0);
    const itemsToShow = 4;
    const isSliding = ref(false);

    const visibleBrands = computed(() => {
      return brands.value.slice(currentIndex.value, currentIndex.value + itemsToShow);
    });

    const triggerSlideAnimation = () => {
      isSliding.value = true;
      setTimeout(() => {
        isSliding.value = false;
      }, 300); // Match animation time
    };

    const slideLeft = () => {
      if (currentIndex.value > 0) {
        currentIndex.value -= itemsToShow;
        triggerSlideAnimation();
      }
    };

    const slideRight = () => {
      if (currentIndex.value + itemsToShow < brands.value.length) {
        currentIndex.value += itemsToShow;
        triggerSlideAnimation();
      }
    };

    const nextPage = () => {
      alert("Navigating to the next page!");
    };

    return {
      visibleBrands,
      slideLeft,
      slideRight,
      nextPage,
      isSliding
    };
  }
};
</script>

<style>
.contents {
  max-width: 100vw;
  padding: 1rem;
  box-sizing: border-box;
}


.links {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
  list-style: none;
  padding: 0;
  margin: 0 auto;
}

.links li {
  flex: 1 1 200px; /* flexible min width */
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.links img {
  max-height: 50px;
  border-radius: 50%;
  flex-shrink: 0;
}

.contents::-webkit-scrollbar {
  width: 8px;
}
.contents::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, 0.3);
  border-radius: 4px;
}


.brands-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  overflow-x: auto;
  padding: 1rem 0;
}

.brand-list {
  display: flex;
  gap: 1rem;
  overflow-x: auto;
  scroll-behavior: smooth;
}

.brand-item {
  min-width: 120px;
  flex-shrink: 0;
}

.brand-item a {
  text-decoration: none;
  color: black;
  font-size: 1.5rem;
  transition: color 0.3s;
}

.brand-item:hover {
  transform: scale(1.05);
  background-color: #e0e0e0;
}

.brand-item:hover a {
  color: #ff5722;
}

.brand-list.sliding {
  animation: slideIn 0.3s ease;
}

@keyframes slideIn {
  0% {
    transform: translateX(50px);
    opacity: 0.3;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

.Arrow {
  cursor: pointer;
  font-size: 5rem;
  padding: 10px;
}
@media (max-width: 768px) {
  .links {
    flex-direction: column;
    align-items: center;
  }
  .links li {
    flex: none;
    width: 100%;
    justify-content: center;
  }
  .brands-container {
    flex-direction: column;
    overflow-x: visible;
  }
  .brand-list {
    flex-wrap: nowrap;
  }
}

@media (max-width: 480px) {
  h1 {
    font-size: 1.5rem;
    margin-top: 1rem;
  }
}
</style>