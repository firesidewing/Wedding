<template>
  <main class="hello">
    <section class="top-banner-section">
      <div class="banner-image-div">
        <picture id="hero" class="banner-image hidden">
          <source media="(min-width:600px)" srcset="@/assets/Hero-min.jpg">
          <source media="(max-width:600px)" srcset="@/assets/Hero-min-small.jpg">
          <img src="@/assets/Hero-min.jpg" >
        </picture>
      </div>

      <div id="over" class="banner-overlay-div"></div>

      <div class="banner-text-div">
        <span class="diff">Josh & Tess</span> <br/>
        <span class="small p1">are getting married!</span> <br/>
        <span class="smaller">May 23, 2021</span>         
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
.diff{
  font-family: 'Poiret One', cursive;
  font-size: 3rem;
}
.small{
  font-size:1.5rem;
}
.smaller {
  font-size: 1rem;
}
.p1{
  font-family: 'Poiret One', cursive;
}
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
  height:100%;
  
  transition: opacity 2s ease-in;
}
.banner-image img{
  object-fit: cover;
  object-position: right;
  min-width: 350px;
  width: 100%;
  height: 100%;
}
.banner-image source {
  display: none;
}

.hidden {
  opacity: 0;
}

.banner-overlay-div {
  display: grid;
  max-width: 100%;
  background: black;
  background: rgba(0, 0, 0, 0.56);
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
