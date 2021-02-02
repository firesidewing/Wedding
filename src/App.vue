<template>
  <div id="app">
    <Nav v-on:theme="ToggleTheme" v-bind:tab.sync="tab" />
    <Home v-show="tab === 'Home'" />
    <Story v-show="tab === 'Story'" />
    <Info v-show="tab === 'Info'" />
    <RSVP v-show="tab === 'RSVP'" />
    <Registry v-show="tab === 'Registry'" />
    <Footer/>
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Home from "./components/Home.vue";
import Story from "./components/Story.vue";
import Info from "./components/Info.vue";
import RSVP from "./components/RSVP.vue";
import Registry from "./components/Registry.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "Main",
  components: {
    Nav,
    Home,
    Story,
    Info,
    RSVP,
    Registry,
    Footer
  },
  data() {
    return {
      Theme: "light",
      ThemeMap: {
        dark: "light",
        light: "solar",
        solar: "dark",
      },
      tab: 'Home'
    };
  },
  created() {
    this.SetTheme()
  },
  methods: {
    SetTheme: function () {
      this.Theme =
        localStorage.getItem("theme") ||
        ((tmp = Object.keys(this.ThemeMap)[0]),
        localStorage.setItem("theme", tmp),
        tmp);
      
      bodyClass.add(this.Theme);
    },
    ToggleTheme: function () {
      const current = localStorage.getItem("theme");
      const next = this.ThemeMap[current];

      bodyClass.replace(current, next);
      localStorage.setItem("theme", next);
    },
  },
};

let tmp
const bodyClass = document.body.classList;
</script>

<style>
:root {
  font-size: 16px;
  font-family: 'Open Sans';
  --text-primary: #b6b6b6;
  --text-secondary: #ececec;
  --bg-primary: #23232e;
  --bg-secondary: #141418;
  --transition-speed: 300ms;
  --btn: #F08E80;
  --control: #576e75;
}

body {
  color: black;
  background-color: white;
  margin: 0;
  padding: 0;
  height:100vh;
  background-color: var(--bg-primary);
  color: var(--text-primary);
  transition: background-color 300ms ease;
  font-family: 'Trirong', serif;
}

main {
  padding: 1rem;
  
}

#app{
  display: grid;
  grid-template-rows: auto 1fr auto;
  justify-content: center;
  height:100%;
}



/* Large screens */
@media only screen and (min-width: 600px) {
  
}

.dark {
  --text-primary: #b6b6b6;
  --text-secondary: #ececec;
  --bg-primary: #23232e;
  --bg-secondary: #141418;
  --control: #b6b6b6;
}

.light {
  --text-primary: #1f1f1f;
  --text-secondary: #000000;
  --bg-primary: #ffffff;
  --bg-secondary: #e4e4e4;
  --control: #9E9E9E;
}

.solar {
  --text-primary: #576e75;
  --text-secondary: #35535c;
  --bg-primary: #fdf6e3;
  --bg-secondary: #f5e5b8;
  --control:  #576e75;
}

.theme-icon {
  display: none;
  height:30px;
}

.dark #darkIcon {
  display: block;
}

.light #lightIcon {
  display: block;
}

.solar #solarIcon {
  display: block;
}
</style>
