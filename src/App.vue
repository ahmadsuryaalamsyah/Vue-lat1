<script setup>
import ClickCounter from './components/ClickCounter.vue';
import BoxCollor from './components/BoxCollor.vue';
import ImageFetcher from './components/ImageFetcher.vue';
</script>

<template>
  <div id="app">
    <nav>
      <h1 id="title">Vue <span id="framework">Framework</span></h1>
    </nav>
    <div id="counter">
      <h2 id="title-box">Click Counter Quotes</h2>
      <ClickCounter />
    </div>
    <div id="batas"></div>
    <div id="box">
      <h2 Box id="title-box">Box Color</h2>
      <BoxCollor />
    </div>
    <div id="batas"></div>
    <div id="box">
      <h2 id="title-box">Fetch Image</h2>
      <ImageFetcher />
    </div>
  </div>
</template>

<style scoped>
#title {
  font-size: 45px;
  font-weight: bold;
  text-align: center;
  text-align: center;
  margin-bottom: 70px;
  color: #28a745;
}

#framework {
  color: #222222;
}

#counter {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}

#batas {
  height: 2px;
  background-color: #28a745;
  margin: 20px 20px;
}

#box {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}

#title-box {
  color: #222222;
  font-size: 28px;
}
</style>
