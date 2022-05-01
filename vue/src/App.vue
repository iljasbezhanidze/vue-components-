<template>
  <div class="root">
     <my-components/>
  </div>
</template>

<script>
import myComponents from './components/myToDoList'

export default {
  name: 'App',
  components: {
    myComponents
  }
}
</script>


