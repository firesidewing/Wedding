<template>
  <div>
    <div>
      <section class="top-banner-section">
        <div class="banner-image-div">
        </div>

        <div id="over" class="banner-overlay-div"></div>

        <div class="banner-text-div">
          <span class="f3 p1">Our Story</span> <br />
          <hr style="width:70%; margin-top:-3px">
        </div>
      </section>
    </div>
    <div class="story-grid">
      <div>
        <div>
          <span class="f2 p1">August 2013</span>
        </div>
        <div>
          <span>Josh & Tess meet while working at the Bohemian Cafe in Kelowna, BC</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">June 2016</span>
        </div>
        <div>
          <span>Tess returns from first year university and deviously convinces Josh to finally date her - just for the summer!</span>
          <br/>
          <span>Josh is hesitant because he doesn't want to go to jail</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">September 2016</span>
        </div>
        <div>
          <span>Break things off due to the distance <br/> (Montreal to BC)</span>
          <br />
          <span>Josh lasts 8 days before deciding to do long distance...</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">September 2017</span>
        </div>
        <div>
          <span>Josh moves to Montreal to be with Tess after graduating from UBCO</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">September 2018</span>
        </div>
        <div>
          <span>Josh & Tess move in to their first appartment together in Montreal</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">December 2018</span>
        </div>
        <div>
          <span>We got Woody!</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">May 2020</span>
        </div>
        <div>
          <span>TESS SAYS YES!!!</span>
        </div>
      </div>
      <div>
        <div>
          <span class="f2 p1 mt-10">July 2020</span>
        </div>
        <div>
          <span>Josh and Tess drive across the country after Tess finishes her degree at McGill</span>
        </div>
      </div>

      <div>
        <div>
          <span class="f2 p1 mt-10">October 2020</span>
        </div>
        <div>
          <span>Bought a house together!</span>
        </div>
      </div>
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

<style scoped>
.mt-10{
  margin-top:5rem;
}
.story-grid{
  display: grid;
  grid-gap: 1rem;
  grid-template-rows: auto;
  background: trnsparent;
}
.story-grid div {
  display:grid;
  grid-gap: 1rem;
  text-align: center;
  margin: auto;
  z-index: 3;
  color: #b6b6b6;
  font-weight:bolder;
}

.main * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.f1{
  font-size:1rem;
}
.f2{
  font-size:2rem;
}
.f3{
  font-size:3rem;
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
.top-banner-section {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 94vh;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  align-content: center;
  justify-content: center;
  margin: 0;
}

.banner-image-div {
  grid-area: 1 / 1 / 2 / 2;
  min-height: 100%;
  z-index: 1;

  background-image: url("~@/assets/boat-min.jpg");
  object-fit: cover;
  width:100vw;
  max-width:100%;

  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: fixed;
  left:0;
  top:0;
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
}
.banner-image img{
  object-fit: cover;
  object-position: center;
  min-width: 350px;
  width: 100%;
  height: 100%;
  margin-top: 1rem;
}
.banner-image source {
  display: none;
}

.banner-overlay-div {
  display: grid;
  max-width: 100%;
  background: black;
  background: rgba(0, 0, 0, 0.56);
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: fixed;
  top:0;
  left:0;
  object-fit: cover;
  width:100vw;
  max-width:100%;
  height:100%;
}

</style>