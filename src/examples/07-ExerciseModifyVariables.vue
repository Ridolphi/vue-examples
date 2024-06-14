<template>
  <div>
    <table>
      <tr v-for="(row, rowIndex) in colors" :key="rowIndex">
        <td v-for="(color, colIndex) in row" :key="colIndex" :style="{ backgroundColor: color }" @click="changeTextColor(color)">
          {{ color }}
        </td>
      </tr>
    </table>
    <p :style="{ color: selectedColor }">Este texto cambia de color! =D</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colors: [
        ['#FF69B4', '#33CC33', '#6666CC'],
        ['#0099CC', '#FFCC00', '#663300'],
        ['#CC0099', '#33CCCC', '#996600']
      ],
      selectedColor: 'black'
    }
  },
  methods: {
    changeTextColor(color) {
      this.selectedColor = color;
    }
  }
}
</script>

<style scoped>

p {
  padding-top: 5.3vh;
  font-size: 18px;
  color: black;
}

table {
  font-size: 5.3vh;
}

</style>