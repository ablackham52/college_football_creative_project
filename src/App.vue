<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/favorites">
        <div class="menu-item">
          <img src="/images/star.png">
          <p>Favorites</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class="footer">
  <a class="github" href='https://github.com/ablackham52/college_football_creative_project' target='_blank'>GitHub Repo</a>
</div>
</div>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: black;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
  text-align: center;
}

#side img {
  width: 50px;
  margin: 10px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

.footer {
  height: 100px;
  margin-top: 100px;
  background-color: #343A40;
  display: flex;
  justify-content: flex-start;
  width: 100%;
  bottom: 0;
}

.github:link, .github:visited {
  color: white;
  background-color: #343A40;
  font-weight: bold;
  text-align: center;
  padding: 10px 10px
}

.github:hover,
.github:visited:hover {
  color: #FFF;
  background-color: #343A40;
  /* Light blue */
}

.github:active,
.github:visited:active {
  color: #FFF;
  background-color: #343A40;
  /* Blue */
}

</style>
