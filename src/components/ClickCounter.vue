<template>
  <div>
    <p class="quote">{{ randomQuote }}</p>
    <button @click="incrementCounter" class="click-button">Lihat Quotes</button>
    <p class="counter">Jumlah klik : {{ counter }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const counter = ref(0);
const quotes = [
  'Kerja keraslah sampai tetangga berpikir rezekimu hasil dari pesugihan',
  'Berhenti Menyalahkan Segalanya !',
  'Percayalah pada dirimu !',
  'Kerjakan dengan Lebih dan Sepenuh Hati',
  'Namanya juga hidup. Pasti banyak cobaan. Kalau banyak cucian ya laundry',
  'Tetap positif, bekerja keras, dan wujudkan mimpimu',
  'Masalah bisa membuat kita semakin dewasa, maka sering-seringlah bermasalah !',
  'Hormati orang tuamu. Mereka lulus sekolah tanpa Google',
  'Berpikirlah seperti proton. Selalu positif',
  'Satu-satunya batasan adalah pikiranmu',
];

const randomQuote = ref('');

const incrementCounter = () => {
  counter.value++;
  randomQuote.value = quotes[Math.floor(Math.random() * quotes.length)];
};
</script>

<style scoped>
.click-button {
  background-color: #28a745;
  color: white;
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
  transition: background-color 0.3s;
}

.click-button:hover {
  background-color: #218838;
}

.counter {
  font-size: 22px;
  margin-top: 20px;
  color: #555;
}

.quote {
  font-size: 25px;
  font-style: italic;
  color: #666;
}
</style>
