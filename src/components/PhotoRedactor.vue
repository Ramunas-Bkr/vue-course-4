<template>
  <div class="photo-redactor">
    <div class="photo-block">
      <img
        v-if="isCatVisible"
        :class="filters"
        src="../assets/images/cat.jpg"
        alt="cat"
        :style="changeImage"
      />
      <p v-else>Cat will be here soon...</p>
    </div>
    <div class="redactor-block">
      <h1>Kebab cat</h1>
      <div class="filters">
        <button
          @click="filters.sepia = !filters.sepia"
          :class="filters.sepia ? 'active' : ''"
        >
          Sepia
        </button>
        <button
          @click="filters.border = !filters.border"
          :class="filters.border ? 'active' : ''"
        >
          Border
        </button>
        <button
          @click="filters.shadow = !filters.shadow"
          :class="filters.shadow ? 'active' : ''"
        >
          Shadow
        </button>
      </div>
      <div class="size">
        <p>Width: {{ imageSize.currentWidth }}</p>
        <input
          :value="imageSize.currentWidth"
          @input="imageSize.currentWidth = $event.target.value"
          type="range"
          :min="imageSize.minWidth"
          :max="imageSize.maxWidth"
        />
        <p>Height: {{ imageSize.currentHeight }}</p>
        <input
          :value="imageSize.currentHeight"
          @input="imageSize.currentHeight = $event.target.value"
          type="range"
          :min="imageSize.minHeight"
          :max="imageSize.maxHeight"
        />
      </div>
      <div class="rotate">
        <p>Rotate: {{ imageRotate.currentDeg }} degree</p>
        <input
        type="range"
        :value="imageRotate.currentDeg"
        @input="imageRotate.currentDeg = $event.target.value"
        :min="imageRotate.minDeg"
        :max="imageRotate.maxDeg"/>
      </div>
      <button @click="isCatVisible = !isCatVisible">
        {{ isCatVisible ? 'Hidden' : 'Show' }}
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: "PhotoRedactor",
  data() {
    return {
      isCatVisible: true,
      filters: {
        sepia: false,
        border: false,
        shadow: false
      },
      imageSize: {
        maxWidth: 640,
        minWidth: 5,
        maxHeight: 424,
        minHeight: 5,
        currentWidth: 640,
        currentHeight: 424
      },
      imageRotate: {
        minDeg: 0,
        maxDeg: 360,
        currentDeg: 0
      }
    };
  },
  computed: {
    changeImage() {
      return {
        width: `${this.imageSize.currentWidth}px`,
        height: `${this.imageSize.currentHeight}px`,
        transform: `rotate(${this.imageRotate.currentDeg}deg)`
      };
    }
  }
};
</script>
<style>
.photo-redactor {
  display: inline-block;
  width: 100%;
  text-align: center;
  margin: 10px 10%;
}
.photo-redactor .photo-block {
  display: inline-block;
  width: 45%;
  text-align: left;
}
.photo-redactor .photo-block img {
  width: 640px;
  height: 424px;
  transition: all 1s;
}
.photo-redactor .photo-block img.sepia {
  filter: sepia(1);
}
.photo-redactor .photo-block img.border {
  border: 4px solid #000;
}
.photo-redactor .photo-block img.shadow {
  box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.75);
}
.photo-redactor .redactor-block {
  display: inline-block;
  width: 50%;
  vertical-align: top;
  text-align: left;
  margin-left: 20px;
}
.photo-redactor .redactor-block button {
  margin-left: 10px;
  transition: all 1s;
}
button.active {
  background-color: blue;
}
.photo-redactor .redactor-block > button {
  margin-top: 20px;
}
</style>
