<template>
<div id="app">
  <!-- <div class="header">
    <router-link to="/">
      <div class="logo">
       <img src="/ordinary.png">
      </div>
    </router-link>
    <div class="title">
      <h1>Sydney's Favorite Recipes</h1>
    </div>
  </div>
  <div class="content">
    <router-view />
  </div>
-->
<nav class="navbar navbar-expand-md navbar-light bg-light">
  <div class="container-fluid">
    <router-link to="/">
      <div class="navbar-brand">Sydney's Favorite Recipes</div>
    </router-link>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link to="/">
            <p class="nav-link">Home</p>
          </router-link>
        </li>
        <li class="nav-item">
          <router-link to="/admin">
            <p class="nav-link">Upload</p>
          </router-link>
        </li>
        <li class="nav-item">
          <router-link to="/about">
            <p class="nav-link">About</p>
          </router-link>
        </li>
      </ul>
    </div>
  </div>
  </nav>
<div class="content">
	<router-view />
</div>
<div class="footer">
  <a href="https://github.com/sallen01/recipes.git" target="_blank">GitHub</a>
</div>
</div>
</template>

<style>
html {
  box-sizing: border-box;
}

body {
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  background: #ebebeb;
  padding: 0px;
  margin: 0px;
}
.nav-item {
  padding-top: 32px;
}
.container-fluid {
  background-color: #E6DFD8;
  border: 1px solid black;
}
.container-fluid a {
  color: black;
}
.router-link-exact-active p {
  font-weight: bold;
  text-decoration: underline;
}
.navbar-brand {
  padding: 5px 15px;
  border: 1px solid black;
}
.navbar-collapse {
  display: flex;
  justify-content: space-between;
}
#navbarSupportedContent {
    height: 80px;
}
h1 {
font-size: 25px;
}
h5 {
font-size: 15px;
}
.content {
  padding: 20px 100px;
  min-height: 500px;
}

/* Footer */
.footer {
  height: 100px;
  padding: 20px 100px 0px 100px;
  background: #E6DFD8;
  font-size: 20px;
}

.footer a {
  color: #000;
}
</style>
