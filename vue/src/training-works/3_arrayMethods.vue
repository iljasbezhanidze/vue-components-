<template>
  <div class="arrays">
    <button @click="addItem">Додати</button>
    <button @click="removeItem">Видалити</button>
    <button @click="reverseItem">Перевернути</button>
    <button @click="sortItem">Сортувати</button>
    <button @click="shuffleItem">Перемішати</button>
    <button @click="evenItem">Лише парні</button>
    <button @click="oddItem">Лише непарні</button>
    <button @click="multiplyItem">Піднести до степеня</button>
    <button @click="divideItem">Навпіл</button>
    <button @click="clearList">Очистити</button>
    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [],
    };
  },

  methods: {
    addItem() {
      this.items.push(Math.floor(Math.random() * 100));
    },

    removeItem() {
      this.items.pop();
    },

    reverseItem() {
      this.items.reverse();
    },

    sortItem() {
      this.items.sort((a, b) => a - b);
    },

    shuffleItem() {
      this.items.sort(() => 0.5 - Math.random());
    },

    clearList() {
      this.items = [];
    },

    evenItem() {
      this.items = this.items.filter((el) => el % 2 === 0);
    },

    oddItem() {
      this.items = this.items.filter((el) => el % 2 !== 0);
    },

    multiplyItem() {
      this.items = this.items.map((el) => el * el);
    },

    divideItem() {
      this.items = this.items.map((el) => Math.floor(el / 2));
    },
  },
};
</script>

<style>
* {
  font-family: monospace;
  font-size: 20px;
}

.arrays {
  max-width: 90%;
}

li {
  display: inline-block;
  margin-inline: 10px;
}

button {
  margin-bottom: 10px;
}
</style>