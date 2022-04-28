<template>
  <div class="b-search">
    <p><b>Пошук товарів</b></p>
    <input type="search" placeholder="Пошук" @input="searchText = $event.target.value" />
    <p>Всього позицій: {{ items.length }}, знайдено: {{ getFilteredItems.length }}</p>
    <ul>
      <li 
      v-for="(position, index) in getFilteredItems" 
      :key="index">
        {{ position }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: 'mySearch',

  data() {
    return {
      searchText: "",
      items: [
        "Телевізори",
        "Мобільні",
        "Смарт годинники",
        "Портативні колонки",
        "Камери",
        "Квадрокоптери",
        `Карти пам'яті`,
        "Action камери",
        "Powerbank",
        "Ноутбуки",
        "Планшети",
        "ПК",
        "WI-FI роутери",
        "Приставки",
        "Монітори",
        "Фотоапарати",
        "Аккумулятори та батарейки",
        "Окуляри віртуальної реальності",
        "Навушники",
        "Аудіосистеми",
        "Колонки",
        "Музичні інструменти",
      ],
    };
  },

  computed: {
    getFilteredItems () {
        return this.items.filter(position => position.toLowerCase().includes(this.searchText.toLowerCase()))
    },
  },
};
</script>

