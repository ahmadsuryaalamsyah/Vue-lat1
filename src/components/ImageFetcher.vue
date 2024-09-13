<template>
  <div>
    <h1 id="title">Random Dog</h1>
    <div class="carousel-container" v-if="dogImages.length">
      <div class="carousel-wrapper" :style="{ transform: `translateX(-${currentImageIndex * 100}%)` }">
        <img v-for="(image, index) in dogImages" :key="index" :src="image" alt="Dog Image" class="carousel-image" />
      </div>
    </div>
    <div class="carousel-controls">
      <button @click="prevImage" class="carousel-button">Prev</button>
      <button @click="nextImage" class="carousel-button">Next</button>
    </div>
    <button id="button" @click="fetchImages">Change Images</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      dogImages: [],
      currentImageIndex: 0,
    };
  },
  methods: {
    async fetchImages() {
      try {
        const response = await axios.get('https://dog.ceo/api/breeds/image/random/5');
        this.dogImages = response.data.message;
        this.currentImageIndex = 0;
      } catch (error) {
        console.error('Error fetching images:', error);
      }
    },
    prevImage() {
      this.currentImageIndex = this.currentImageIndex > 0 ? this.currentImageIndex - 1 : this.dogImages.length - 1;
    },
    nextImage() {
      this.currentImageIndex = this.currentImageIndex < this.dogImages.length - 1 ? this.currentImageIndex + 1 : 0;
    },
  },
  mounted() {
    this.fetchImages();
  },
};
</script>

<style scoped>
img {
  width: 300px;
  height: auto;
  display: block;
  margin: 10px auto;
}

#title {
  font-size: 28px;
  text-align: center;
  color: #222222;
}

.carousel-container {
  position: relative;
  width: 200px;
  height: auto;
  overflow: hidden;
  margin: 0 auto;
}

.carousel-wrapper {
  display: flex;
  transition: transform 0.5s ease;
}

.carousel-image {
  min-width: 100%;
  height: auto;
}

.carousel-controls {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
}

.carousel-button {
  background-color: #28a745;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.carousel-button:hover {
  background-color: #218838;
}

#button {
  width: 100%;
  margin-top: 40px;
  background-color: #28a745;
  color: white;
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
  transition: background-color 0.3s;
}

#button:hover {
  background-color: #218838;
}
</style>
