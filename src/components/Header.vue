<template>
  <nav class="header">
    <div class="slider-container">
      <span class="arrow" @click="slideLeft">&#8249;</span>

      <transition
        :name="transitionName"
        mode="out-in"
      >
        <p class="slide-message" :key="currentIndex">
          &lt; {{ messages[currentIndex] }} &gt;
        </p>
      </transition>

      <span class="arrow" @click="slideRight">&#8250;</span>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      messages: [
        "Welcome to My Vue App!",
        "Welcome to My Show!",
        "Explore the Power of Vue!",
      ],
      currentIndex: 0,
      direction: 'right', // track direction for animation
    };
  },
  computed: {
    transitionName() {
      // Slide left if direction is left, otherwise slide right
      return this.direction === 'left' ? 'slide-left' : 'slide-right';
    }
  },
  methods: {
    slideLeft() {
      this.direction = 'left';
      if (this.currentIndex === 0) {
        this.currentIndex = this.messages.length - 1;
      } else {
        this.currentIndex--;
      }
    },
    slideRight() {
      this.direction = 'right';
      if (this.currentIndex === this.messages.length - 1) {
        this.currentIndex = 0;
      } else {
        this.currentIndex++;
      }
    }
  }
}
</script>

<style scoped>
.header {
  width: 100vw;
  background-color: orangered;
  padding: 1rem 0;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  height: 60px;
  box-sizing: border-box;
  margin: 0;
}

.slider-container {
  display: flex;
  align-items: center;
  justify-content: center;
  max-width: 90vw; /* instead of fixed 560px */
  margin: 0 auto; /* center horizontally */
  background-color: orangered;
  padding: 0 1rem;
  box-sizing: border-box;
  gap: 1rem;
  position: relative;
  bottom: 0; /* remove large bottom offset */
  left: 0; /* remove large left offset */
}

@media (max-width: 768px) {
  .slider-container {
    max-width: 100%;
    padding: 0 0.5rem;
  }
  .slide-message {
    font-size: 1rem;
  }
  .arrow {
    font-size: 1.2rem;
  }
}
@media (max-width: 480px) {
  .slide-message {
    font-size: 0.9rem;
  }
  .arrow {
    font-size: 1rem;
  }
}

.arrow {
  cursor: pointer;
  font-size: 1.5rem;
  user-select: none;
  color: black;
  font-weight: bold;
}

.message-wrapper {
  flex: 1;
  overflow: hidden;
  white-space: nowrap;
  position: relative;
  color: white;
  font-family: monospace;
  font-weight: bold;
  text-align: center;
}

.slide-message {
  font-family: monospace;
  font-weight: bold;
  font-size: 1.1rem;
  margin: 0 1rem;
}

/* Slide right animation */
.slide-right-enter-active,
.slide-right-leave-active {
  transition: transform 0.4s ease, opacity 0.4s ease;
  position: absolute;
  width: 100%;
  left: 0;
}

.slide-right-enter-from {
  transform: translateX(100%);
  opacity: 0;
}

.slide-right-enter-to {
  transform: translateX(0);
  opacity: 1;
}

.slide-right-leave-from {
  transform: translateX(0);
  opacity: 1;
}

.slide-right-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}

/* Slide left animation */
.slide-left-enter-active,
.slide-left-leave-active {
  transition: transform 0.4s ease, opacity 0.4s ease;
  position: absolute;
  width: 100%;
  left: 0;
}

.slide-left-enter-from {
  transform: translateX(-100%);
  opacity: 0;
}

.slide-left-enter-to {
  transform: translateX(0);
  opacity: 1;
}

.slide-left-leave-from {
  transform: translateX(0);
  opacity: 1;
}

.slide-left-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
</style>
