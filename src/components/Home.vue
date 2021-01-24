<template>
  <main class="hello">
    <section class="top-banner-section">
      <div class="banner-image-div">
        <img
          class="banner-image hidden"
          id="hero"
          src="@/assets/Hero-min.jpg"
          alt="Banner Image"          
        />
      </div>

      <div id="over" class="banner-overlay-div"></div>

      <div class="banner-text-div">
        <span>May 23rd 2021</span>
        <p>
          <a class="map-link" href="https://goo.gl/maps/YQdVBMBpsmZ9Fpog6" target="_blank">
            <i class="gg-pin"></i>
            <span>Directions</span>
          </a>
        </p>        
      </div>
      
    </section>
  </main>
</template>

<script>
export default {
  name: "Home",
  mounted() {
    let img = document.getElementById('hero')
    setTimeout(() => img.classList.remove('hidden'), 100)
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.top-banner-section {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 94vh;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  align-content: center;
  justify-content: center;
  margin: -1rem -1rem;
}

.banner-image-div {
  grid-area: 1 / 1 / 2 / 2;
  z-index: 1;
}
.banner-overlay-div {
  grid-area: 1 / 1 / 2 / 2;
  z-index: 2;
}
.banner-text-div {
  grid-area: 1 / 1 / 2 / 2;
  margin: auto;
  font-size:2rem;
  font-weight:bolder;
  color: #b6b6b6;
  text-align: center;
  z-index: 3;
}

.banner-image {
  display: grid;
  min-width: 350px;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: right;
  transition: opacity 2s ease-in;
}

.hidden {
  opacity: 0;
}

.banner-overlay-div {
  display: grid;
  max-width: 100%;
  background: black;
  background: rgba(0, 0, 0, 0.76);
}

.map-link {
  display:flex;
  justify-content: space-around;
  align-items: center;
  text-decoration: none;
  color: #b6b6b6;
}

.gg-pin {
    box-sizing: border-box;
    position: relative;
    display: block;
    transform: rotate(45deg) scale(var(--ggs,1));
    width: 18px;
    height: 18px;
    border-radius: 100% 100% 0 100%;
    border: 2px solid;
    margin-top: -4px
}
.gg-pin::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    width: 8px;
    height: 8px;
    border: 2px solid;
    top: 3px;
    left: 3px;
    border-radius: 40px
}

@media only screen and (max-width: 600px) {
  .top-banner-section{
    height:87vh;
    margin: 0;
    grid-template-rows: 87vh;
  }
  main{
    padding:0;
  }
}

</style>
