<template>
  <div>
    <button @click="changeColor" id="change-color">Change Box Color</button>
    <div :style="{ backgroundColor: boxColor }" class="box"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      boxColor: 'green',
    };
  },
  methods: {
    changeColor() {
      const colors = ['red', 'green', 'blue', 'yellow', 'purple', 'orange'];
      this.boxColor = colors[Math.floor(Math.random() * colors.length)];
    },
  },
};
</script>

<style>
.box {
  width: 200px;
  height: 200px;
  margin-top: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  border-radius: 5px;
}

#change-color {
  background-color: #28a745;
  color: white;
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
  transition: background-color 0.3s;
}
#change-color:hover {
  background-color: #218838;
}

button {
  margin-top: 20px;
}
</style>
