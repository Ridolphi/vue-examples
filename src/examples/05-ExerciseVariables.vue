<template>
  <div>
    <div class="post-it" @mouseover="changeColor" :style="{ backgroundColor: currentColor }">
      <p>{{ note }}</p>
    </div>
    <div class="array-container">
      <p>{{ formattedString }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      note: "Hey, this is a Post... it!",
      stringsArray: ['a', 'b', 'c'],
      colors: ["yellow", "lightblue", "lightgreen", "lightcoral"],
      currentColor: "yellow"
    };
  },
  computed: {
    formattedString() {
      return this.stringsArray.join('-');
    }
  },
  methods: {
    changeColor() {
      const randomIndex = Math.floor(Math.random() * this.colors.length);
      this.currentColor = this.colors[randomIndex];
    }
  }
};
</script>

<style scoped>
.post-it {
  padding: 10px;
  border: 2px solid black;
  width: 20vh;
  height: 20vh;
  text-align: center;
  align-content: center;
  color: red;
}

p {
  font-weight: bold;
}

.array-container {
  color: black;
  padding-top: 10vh;
  font-size: 3.5vh;
}
</style>
