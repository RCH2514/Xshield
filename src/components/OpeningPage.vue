<template>
    <div class="opening-page">
      <video class="background-video" autoplay muted loop>
        <source src="@/assets/videos/vid1.mp4" type="video/mp4" />
        Your browser does not support the video tag.
      </video>
      <div class="content-container">
      <!--<img src="@/assets/images/logo.png" alt="Logo" class="logo" />-->
      <div :class="{'button-container': true, 'show-button': showButton}">
        <button class="button-86" role="button" @click="goToHomePage">Enter</button>
      </div>
   
    </div>
    </div>
  </template>
  
  <script>
 export default {
  data() {
    return {
      showButton: false
    };
  },
  mounted() {
    // Delay button appearance by 3 seconds
    setTimeout(() => {
      this.showButton = true;
    }, 3000); // 3000 milliseconds = 3 seconds
  },
  methods: {
    goToHomePage() {
      this.$router.push({ name: 'AppHome' }); // Navigate to home page
    }
  }
}
  </script>
  
  <style scoped>
  .opening-page {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    display: flex;
  align-items: center;
  justify-content: center;
  background: #000; /* Fallback background color */
  }
  .content-container {
  position: absolute;
  top: 25%;
  left: 80%;
  transform: translate(-50%, -50%);
  text-align: center;
}
  .background-video {
    position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  /*z-index: -1; Ensure the video is behind the content */
  opacity: 0.5; /* Set video opacity to 0.5 */
   
  }
  
  .button-container {
    opacity: 0;
  transition: opacity 1s ease-in-out; /* Smooth transition */
  margin-top: 20px;
}
  

  .logo {
  width: 150px; /* Adjust size as needed */
  animation: bounce 2s infinite; /* Apply animation */
}
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-30px);
  }
  60% {
    transform: translateY(-15px);
  }
}
.show-button {
  opacity: 1;
}
.button-86 {
  all: unset;
  width: 100px;
  height: 30px;
  font-size: 16px;
  background: transparent;
  border: none;
  position: relative;
  color: #f0f0f0;
  cursor: pointer;
  z-index: 1;
  padding: 10px 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  white-space: nowrap;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-86::after,
.button-86::before {
  content: '';
  position: absolute;
  bottom: 0;
  right: 0;
  z-index: -99999;
  transition: all .4s;
}

.button-86::before {
  transform: translate(0%, 0%);
  width: 100%;
  height: 100%;
  background: rgba(6,96,121,255);
  border-radius: 10px;
}

.button-86::after {
  transform: translate(10px, 10px);
  width: 35px;
  height: 35px;
  background: #ffffff8b;
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border-radius: 50px;
}

.button-86:hover::before {
  transform: translate(5%, 20%);
  width: 110%;
  height: 110%;
}

.button-86:hover::after {
  border-radius: 10px;
  transform: translate(0, 0);
  width: 100%;
  height: 100%;
}

.button-86:active::after {
  transition: 0s;
  transform: translate(0, 5%);
}
  </style>
