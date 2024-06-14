<template>
  <div class="flex flex-col gap-5 w-full items-center">
    <button
      class="w-32 border-2 rounded-lg bg-gray-100 hover:bg-blue-100 border-blue-400"
      v-on:click="increment"
    >
      Add one
    </button>
    <button
      class="w-32 border-2 rounded-lg bg-gray-100 hover:bg-blue-100 border-blue-400"
      v-on:click="increment(2)"
    >
      Add two!
    </button>
    <p>{{ count }}</p>
    <button
      class="w-32 border-2 rounded-lg bg-gray-100 hover:bg-blue-100 border-blue-400"
      v-on:click="changeButtonText"
    >
      {{ buttonText }}
    </button>
    <button
      class="w-32 border-2 rounded-lg bg-gray-100 hover:bg-blue-100 border-blue-400"
      v-on:mouseover="changeHoverButtonText"
    >
      {{ hoverButtonText }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      buttonText: "Click me!",
      hoverButtonText: "Hover over me!",  
      possibleTitles: ["Hello!", "Click me again!", "Press here!", "Try this!", "Oh no, again!"]
    }
  },
  methods: {
    increment(value) {
      if (Number.isInteger(value)) {
        this.count += value;
      } else {
        this.count++;
      }
    },
    changeButtonText() {
      const randomIndex = Math.floor(Math.random() * this.possibleTitles.length);
      this.buttonText = this.possibleTitles[randomIndex];
    },
    changeHoverButtonText() {
      const randomIndex = Math.floor(Math.random() * this.possibleTitles.length);
      this.hoverButtonText = this.possibleTitles[randomIndex];
    }
  }
}
</script>

<style scoped>
.flex {
  display: flex;
  flex-direction: column;
  gap: 20px;
  align-items: center;
}

.w-32 {
  width: 8rem;
}

.border-2 {
  border-width: 2px;
}

.rounded-lg {
  border-radius: 0.5rem;
}

.bg-gray-100 {
  background-color: #f7fafc;
}

.hover\:bg-blue-100:hover {
  background-color: #ebf8ff;
}

.border-blue-400 {
  border-color: #63b3ed;
}
</style>
