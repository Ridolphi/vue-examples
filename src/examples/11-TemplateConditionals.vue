<script>
export default {
  data() {
    return {
      selectedCountry: ''
    }
  }
}
</script>


<template>
  <div id="app">
    <h1>Countries</h1>

    <div class="country-container">
      <div class="country-item">
        <button @click="selectedCountry = 'brazil'">Brazil</button>
        <img v-if="selectedCountry === 'brazil'" src="@/assets/brasil.avif" alt="Brazil flag">
      </div>

      <div class="country-item">
        <button @click="selectedCountry = 'spain'">Spain</button>
        <img v-if="selectedCountry === 'spain'" src="@/assets/spain.png" alt="Spain flag">
      </div>

      <div class="country-item">
        <button @click="selectedCountry = 'france'">France</button>
        <img v-if="selectedCountry === 'france'" src="@/assets/france.webp" alt="France flag">
      </div>

      <div class="country-item">
        <button @click="selectedCountry = 'italy'">Italy</button>
        <img v-if="selectedCountry === 'italy'" src="@/assets/italy.webp" alt="Italy">
      </div>
    </div>
  </div>
</template>

<style scoped>
h1{
  font-size: 50px;
  text-align: center;
  font-weight: bold;
}
.country-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: flex-start; 
  gap: 30px; 
}

.country-item {
  text-align: center;
}

.country-item button {
  margin-bottom: 10px;
}

.country-item img {
  display: block;
  width: 200px; 
  height: auto;
}

.country-container button {
  border: 2px solid #0b999e; 
  padding: 10px 20px; 
  font-size: 16px; 
  background-color: #afc5df; 
  color: #000000; 
  cursor: pointer;
  transition: all 0.5s ease;
}

</style>
