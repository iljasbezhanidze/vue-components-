<template>
  <div class="b-pagination">
      <button @click="prevPage()">Назад</button>
      <button 
        v-for="(item, index) in pages" 
        :key="index"
        @click="currentPage = index + 1"
        :class="{ activePage: currentPage == index + 1 }"
        >{{ index + 1 }}
      </button>
      <button @click="nextPage()">Вперед</button>
      <p>Сторінка {{ currentPage }} з {{ pages }}</p>
  </div>
</template>

<script>
export default {
    name: 'myPagination',

  data() {
    return {
      pages: 5,
      currentPage: 1
    };
  },

  methods: {
     prevPage() {
       if(this.currentPage > 1) this.currentPage--
     },

     nextPage() {
       if(this.currentPage < this.pages) this.currentPage++
     },

     loadPage(index) {
       console.log(`Завантаження сторінки ${index}`)
     }
  },
  
  watch: {
    currentPage(index) {
      this.loadPage(index)
    }
  }
};
</script>

<style scoped>
  .activePage {
    background: limegreen;
  }
  .b-pagination button:active {
    background: limegreen;
  }
</style>