<template>
    <div class="b-counter">
        <div>Оберіть кількість</div>
        <button @click="decrease">Меньше</button>
        <input type="number" 
        :value="counter"
        :min="min"
        :max="max">
        <button @click="increase">Більше</button>
    </div>
</template>

<script>
export default {
   name: 'myCounter',
   data() {
       return {
           counter: 0,
           max: 10,
           min: 0
       }
   },
   methods: {
       decrease() {
            if(this.counter > this.min) this.counter--
       },
       increase() {
           if(this.counter < this.max) this.counter++
       },
   }
}
</script>
