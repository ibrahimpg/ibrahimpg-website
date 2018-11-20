<template>
  <div id="app">
    <transition name="fade">
      <div id="nav" v-if="this.$route.path !== '/'">
        <router-link to="/"><div>Home</div></router-link>
        <router-link to="/about"><div>About</div></router-link>
        <router-link to="/portfolio"><div>Portfolio</div></router-link>
        <router-link to="/contact"><div>Contact</div></router-link>
      </div>
    </transition>
    <transition :name="transitionName" mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      transitionName: 'fade',
    };
  },
  watch: {
    $route(to, from) {
      if (to.path === '/' || from.path === '/') {
        return this.transitionName = 'slide';
      }
      this.transitionName = 'fade';
    },
  },
};
</script>

<style>

* {
  margin: 0;
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

a {
  color: #EB5160;
  text-decoration: none;
}

h1 {
  color: navy;
  font-weight: 100;
  line-height: 1.5;
}

h3 {
  color: navy;
  font-weight: 100;
  line-height: 1.5;
}

p {
  color: rgba(245,245,245,0.9);
  font-weight: 100;
  line-height: 1.9;
  letter-spacing: 0.5px;
}

hr {
    height: 1px;
    border: 0;
    border-top: 1px solid rgba(245,245,245,0.9);
    padding: 0; 
}

#app {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background: url("./assets/sq.jpg") no-repeat center;
  background-size: cover;
}

#nav {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 10vh;
  position: fixed;
  top: 0;
  z-index: 2;
  width: 100%;
}

#nav a { font-weight: bold; color: #EB5160; border-bottom: 3px solid transparent; margin: 0 5px; padding: 5px; }
#nav a.router-link-exact-active { border-bottom: 3px solid #EB5160; }

.container {
  height: 90vh;
  background-color: rgba(0,0,0,0.85);
  position: fixed;
  bottom: 0;
  width: 100vw;
  overflow-y: auto;
  display: flex;
  justify-content: center;
  padding: 0 15px;
  z-index: 1;
}

.fade-enter-active, .fade-leave-active { transition: opacity 0.35s; }
.fade-enter, .fade-leave-to { opacity: 0; }

.slide-leave-active, .slide-enter-active { transition: 0.8s; }
.slide-enter { transform: translate(0%, 100%); }
.slide-leave-to { transform: translate(0%, 100%); }

.mobileSpace {
  height: 60px;
  display: none;
}

@media only screen and (max-width: 500px) {
  #nav { background-color: #F1F2F6; }
  h1 { font-size: 26px; }
  h3 { font-size: 15px; }
  .mobileSpace { display: block; }
}

@media only screen and (max-width: 400px) {
  h1 { font-size: 26px; }
  h3 { font-size: 12px; }
}

</style>
