<template>
  <div class="container">
    <div style="width: 600px; text-align: center;"><br><br>

      <div class="mobileSpace"></div>

      <p>
        This is a sample of my work. You can check out the rest of my stuff
        <a href="https://github.com/ibrahimpg" target="_blank">on Github.</a>
      </p>

      <br>

      <div id="portfolio">
        <div>
          <p><b>Felstriker</b></p>
          <p>Comprehensive rogue class guide for WoW Classic.</p><br>
          <p><a href="https://felstriker.com" target="_blank">Visit Web App</a></p>
        </div>
        <div>
          <p><b>Venomgram</b></p>
          <p>Instagram clone built with fullstack JavaScript (SPA/PWA).</p><br>
          <p><a href="https://venomgram.netlify.com" target="_blank">Visit Web App</a></p>
          <p><a href="https://github.com/ibrahimpg/venomgram-ui" target="_blank">View UI Code</a></p>
          <p><a href="https://github.com/ibrahimpg/venomgram-server" target="_blank">View Server Code</a></p>
        </div>
        <div>
          <p><b>Nanoca.sh</b></p>
          <p>Modern responsive website built using CSS Grid and the Fetch API.</p><br>
          <p><a href="https://nanoca.sh" target="_blank">Visit Web App</a></p>
        </div>
        <div>
          <p><b>REST-EZ</b></p>
          <p>Boilerplate REST API with pre-built registration routes for Node.js.</p><br>
          <p><a href="https://github.com/ibrahimpg/REST-EZ" target="_blank">View Code</a></p>
        </div>
        <div>
          <p><b>Node Mail List Manager</b></p>
          <p>A Node.js API for building, managing, and interacting with a mailing list.</p><br>
          <p><a href="https://github.com/ibrahimpg/node-mail-list-manager" target="_blank">View Code</a></p>
        </div>
        <div>
          <p><b>Name the 50 states</b></p>
          <p>A fun little quiz built with Vue.</p><br>
          <p><a href="https://ibrahimpg.github.io/50states/" target="_blank">Visit Web App</a></p>
          <p><a href="https://github.com/ibrahimpg/50states" target="_blank">View Code</a></p>
        </div>
      </div>

    <br><br></div>
  </div>
</template>

<style scoped>

#portfolio {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

#portfolio > div {
  height: 250px;
  width: 250px;
  border: 1px solid rgba(245,245,245,0.9);
  margin: 15px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 15px 3px 0 3px;
}

</style>
