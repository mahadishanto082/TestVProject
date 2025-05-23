<template>
  <nav class="header">
    <div class="slider-container">
      <span class="arrow" @click="slideLeft">&#8249;</span> <!-- ‹ -->
      <div class="message-wrapper">
        <p class="slide-message" v-for="(message, index) in messages" :key="index">
          &lt; {{ message }} &gt;
        </p>
      </div>
      <span class="arrow" @click="slideRight">&#8250;</span> <!-- › -->

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
    };
  },
  methods: {
    slideLeft() {
      alert("Left clicked!"); // Placeholder action
    },
    slideRight() {
      alert("Right clicked!"); // Placeholder action
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
  
width: 560px; 
  position: relative;
  left: 65rem;
  background-color: orangered;
  padding: 0 1rem;
  box-sizing: border-box;
  gap: 1rem;
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
  font-family: bold;
}

.slide-message {
  display: inline-block;
  padding-left: 100%;
  animation: slide-left 10s linear infinite;
  font-family: monospace;
}
@keyframes slide-left {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(-100%);
  }
}


</style>
