<template>
  <div class="gallery">
    <div class="image--container">
      <h1 class="loader" v-if="loading">Loading...</h1>
      <img
        src="@/assets/1.jpg"
        @click="selected = 1"
        v-if="selected == 1"
        v-bind:class="{
          'animate-entrance': selected == 1,
          'image--gallery': selected == 1,
        }"
      />
      <img
        src="@/assets/2.jpg"
        @click="selected = 2"
        v-if="selected == 2"
        v-bind:class="{ 'animate-entrance': selected == 2, 'image--gallery': selected == 2, }"
      />
      <img
        src="@/assets/3.jpg"
        @click="selected = 3"
        v-if="selected == 3"
        v-bind:class="{ 'animate-entrance': selected == 3, 'image--gallery': selected == 3 }"
      />
      <img
        src="@/assets/4.jpg"
        @click="selected = 4"
        v-if="selected == 4"
        v-bind:class="{ 'animate-entrance': selected == 4, 'image--gallery': selected == 4 }"
      />
      <img
        src="@/assets/5.jpg"
        @click="selected = 5"
        v-if="selected == 5"
        v-bind:class="{ 'animate-entrance': selected == 5, 'image--gallery': selected == 5 }"
      />
      <img
        src="@/assets/6.jpg"
        @click="selected = 6"
        v-if="selected == 6"
        v-bind:class="{ 'animate-entrance': selected == 6, 'image--gallery': selected == 6 }"
      />
      <img
        src="@/assets/7.jpg"
        @click="selected = 7"
        v-if="selected == 7"
        v-bind:class="{ 'animate-entrance': selected == 7, 'image--gallery': selected == 7 }"
      />
      <img
        src="@/assets/8.jpg"
        @click="selected = 8"
        v-if="selected == 8"
        v-bind:class="{ 'animate-entrance': selected == 8, 'image--gallery': selected == 8 }"
      />
      <img
        src="@/assets/9.jpg"
        @click="selected = 9"
        v-if="selected == 9"
        v-bind:class="{ 'animate-entrance': selected == 9, 'image--gallery': selected == 9 }"
      />
      <img
        src="@/assets/10.jpg"
        @click="selected = 10"
        v-if="selected == 10"
        v-bind:class="{ 'animate-entrance': selected == 10, 'image--gallery': selected == 10 }"
      />
    </div>
    <div class="image--selection">
      <img
        src="@/assets/1-min.jpg"
        @click="selected = 1"
        class="image__item"
      />
      <img
        src="@/assets/2-min.jpg"
        class="image__item"
        @click="selected = 2"        
      />
      <img
        src="@/assets/3.jpg"
        class="image__item"
        @click="selected = 3"        
      />
      <img
        src="@/assets/4.jpg"
        class="image__item"
        @click="selected = 4"        
      />
      <img
        src="@/assets/5.jpg"
        class="image__item"
        @click="selected = 5"        
      />
      <img
        src="@/assets/6.jpg"
        class="image__item"
        @click="selected = 6"        
      />
      <img
        src="@/assets/7.jpg"
        class="image__item"
        @click="selected = 7"        
      />
      <img
        src="@/assets/8.jpg"
        class="image__item"
        @click="selected = 8"        
      />
      <img
        src="@/assets/9.jpg"
        class="image__item"
        @click="selected = 9"        
      />
      <img
        src="@/assets/10.jpg"
        class="image__item"
        @click="selected = 10"        
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "Story",
  data() {
    return {
      loading: false,
      selected: 0,
    };
  },
  mouted() {},
  methods: {},
};
</script>

<style>
.main * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.gallery {
  padding: 0 0.5rem;
  height: 100vh;
}

.image--gallery {
  height: 32rem;
  display: block;
  margin: auto;
  border: 5px solid #222;
  object-fit: cover;
}

.image--selection {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(9rem, 1fr));
  justify-content: center;
  align-items: center;
}

.image__item {
  width: 100%;
  height: 8rem;
  display: block;
  margin: auto;
  border: 5px solid #222;
  object-fit: cover;
  cursor: pointer;
}
.loader {
  text-align: center;
  margin-top: 20%;
  color: #fff;
  font-family: "Open Sans", sans-serif;
  font-weight: 700;
}

.animate-entrance {
  animation: BounceIn 0.8s;
}

@keyframes BounceIn {
  0% {
    transform: scale(0.8);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

@media only screen and (max-width: 600px) {
  .image--selection {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(9rem, 1fr));
    grid-gap: 0.5rem;
    justify-content: center;
    align-items: center;
  }
  .image__item {
    height: 15rem;
    display: block;
    margin: auto;
    border: none;
    object-fit: cover;
  }
  .image--gallery {
    display: none;
  }
}
</style>