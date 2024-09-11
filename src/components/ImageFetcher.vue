<template>
  <div>
    <h1 id="title">Random Dog Image</h1>
    <div id="box-images" v-if="dogImages.length">
      <img v-for="(image, index) in dogImages" :key="index" :src="image" alt="Dog Image" />
    </div>
    <button id="button" @click="fetchImages">Change Image</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      dogImages: [],
    };
  },
  methods: {
    async fetchImages() {
      try {
        const response = await axios.get('https://dog.ceo/api/breeds/image/random/3');
        this.dogImages = response.data.message;
      } catch (error) {
        console.error('Error fetching images:', error);
      }
    },
  },
  mounted() {
    this.fetchImages();
  },
};
</script>

<style scoped>
img {
  width: 200px;
  height: auto;
  display: block;
  margin: 10px auto;
}

#box-images {
  display: flex;
  gap: 20px;
}

#button {
  margin-top: 60px;
  margin-left: 50%;
  margin-right: 50%;
  transform: translate(-50%, -50%);
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
#title {
  text-align: center;
  color: #666;
}
</style>
