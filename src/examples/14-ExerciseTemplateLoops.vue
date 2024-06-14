<template>
  <div class="gallery">
    <div class="image-row" v-for="(row, rowIndex) in imageRows" :key="rowIndex">
      <div v-for="(image, index) in row" :key="image.id" class="image-item">
        <img :src="image.src" :alt="image.alt" @click="removeImage(rowIndex, index)">
      </div>
    </div>
  </div>
</template>

<script>
import brasilAvif from '@/assets/brasil.avif';
import spainPng from '@/assets/spain.png';
import franceWebp from '@/assets/france.webp';
import italyWebp from '@/assets/italy.webp';
import argentinaPng from '@/assets/argentina.png';
import germanyPng from '@/assets/germany.png';

export default {
  data() {
    return {
      images: [
        { id: 1, src: brasilAvif, alt: 'Brazil' },
        { id: 2, src: spainPng, alt: 'Spain' },
        { id: 3, src: franceWebp, alt: 'France' },
        { id: 4, src: italyWebp, alt: 'Italy' },
        { id: 5, src: argentinaPng, alt: 'Argentina' },
        { id: 6, src: germanyPng, alt: 'Germany' }
      ],
      imagesPerRow: 3
    };
  },
  computed: {
    imageRows() {
      let rows = [];
      for (let i = 0; i < this.images.length; i += this.imagesPerRow) {
        rows.push(this.images.slice(i, i + this.imagesPerRow));
      }
      return rows;
    }
  },
  methods: {
    removeImage(rowIndex, imageIndex) {
      const indexToRemove = rowIndex * this.imagesPerRow + imageIndex;
      this.images.splice(indexToRemove, 1);
    }
  }
};
</script>

<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.image-row {
  display: flex;
  justify-content: center;
}

.image-item {
  margin: 10px;
  cursor: pointer;
}

.image-item img {
  width: 200px;
  height: auto;
  border: 1px solid #ccc;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}
</style>