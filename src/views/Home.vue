<template>
  <div class="container" style="background-color: transparent;">
    <div style="transform: translate(0, -5vh); display: flex; flex-direction: column;
    justify-content: center; align-items: center; height: 100%;">
      <h1>Ibrahim P.G.</h1>
      <h3>Fullstack JavaScript Web Development</h3>
      <div class="homeNav">
        <router-link to="/about"><div>About</div></router-link>
        <router-link to="/portfolio"><div>Portfolio</div></router-link>
        <router-link to="/contact"><div>Contact</div></router-link>
      </div>
    </div>
  </div>
</template>

<style scoped>

.homeNav {
  display: flex;
  justify-content: space-between;
  width: 315px;
}

@media only screen and (max-width: 500px) {
  .homeNav { width: 260px; }
}

@media only screen and (max-width: 400px) {
  .homeNav { width: 220px; }
}

</style>
