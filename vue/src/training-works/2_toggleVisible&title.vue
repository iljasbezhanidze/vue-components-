<template>
  <div class="toggle">
    <button
      @click="visible = !visible"
      :title="visible ? 'Click to hide' : 'Click to show'"
    >
      {{ textMethod }}
    </button>
    <h1 v-show="visible">Title</h1>
  </div>
</template>

<script>
export default {
    data() {
        return {
            visible: false
        }
    },

    computed: {
      textMethod() {
        return this.visible ? 'Hide' : 'Show'
    }
  }
}
</script>