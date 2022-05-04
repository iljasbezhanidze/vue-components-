<template>
  <div class="str">
    <button @click="toggleRegister">Змінити</button>
    <h1>{{ text }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "register",
      flag: false,
    };
  },
  methods: {
    toggleRegister() {
      this.flag = !this.flag;
      this.getFlag();
    },

    getFlag() {
      this.flag ? this.change() : (this.text = this.text.toLowerCase());
    },

    upperCaseFirst() {
      this.text = this.text[0].toUpperCase() + this.text.substring(1);
    },

    upperCaseLast() {
      this.text = this.text.replace(
        /.{1}$/,
        `${this.text.slice(-1).toUpperCase()}`
      );
    },

    change() {
      this.upperCaseFirst();
      this.upperCaseLast();
    },
  },
};
</script>