<template>
  <div class="b-image-editor">
   <div class="b-image-editor__wrapper">
        <div class="inner">
            <img src="https://www.cmzoo.org/wp-content/uploads/hedgehog2-400x600.jpg"
            :class="filters"
            :style="imgStyles"/>
        </div>
        <div class="b-image-editor__inner">
            <button 
            @click="filters.border = !filters.border"
            :class="filters.border ? 'active' : ''"
            >border</button>
            <button 
            :class="filters.shadow ? 'active' : '' "
            @click="filters.shadow = !filters.shadow">shadow</button>
            <label>border radius {{ filters.radius }} %
                <input type="range"
                :min="filters.min"
                :max="filters.max"
                :value="filters.radius"
                @input="filters.radius = $event.target.value">
            </label>
        </div>
   </div>
  </div>
</template>

<script>
export default {
  name: "myImageEditor",

  data() {
    return {
      filters: {
        shadow: false,
        radius: 0,
        min: 0,
        max: 100
      },
    }
  },
  computed: {
      imgStyles() {
          return {
              borderRadius: `${this.filters.radius}%`
          }
      }
  }
};

</script>

<style>
label,
input {
    max-width: 300px;
    margin: 20px;
    font-size: 20px;
    display: block;
}
input {
    margin-top: 10px;
    margin-left: 0;
}

.b-image-editor__wrapper {
    display: flex;
}
.b-image-editor__inner {
    flex: 0 0 50%;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
img {
    display: block;
    border: 5px solid transparent;
    margin-bottom: 20px;
}
img.border {
  border: 5px dotted rgb(13, 127, 233);
}
img.shadow {
  box-shadow: 10px 10px 5px #ccc;
}
button {
    max-width: 100px;
    margin: 20px;
    height: 40px;   
}

button.active {
    background: grey;
}
</style>