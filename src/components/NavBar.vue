<template>
  <div id="nav-bar" class="pt-3 pb-3">
    <img alt="Vue logo" src="@/../public/images/logo.png">
    <nav id="navLinks">
      <router-link to="/">Home</router-link> |
      <router-link to="/stats">Country Stats</router-link> |
      <router-link to="/news">News</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
  </div>
  <router-view/>
</template>

<style>
#nav-bar{
  height: 120px;
  width: 100%;
  color: white;
  font-size: 30px;
  background-image: linear-gradient(rgb(0, 0, 0),rgb(0, 20, 51));
  position: fixed;
}

#nav-bar a{
  color: white;
  transition: 200ms;
}

#nav-bar a:hover{
  text-decoration: none;
  color:rgb(34, 197, 197);
}

#navLinks a.router-link-active{
  color: rgb(34, 197, 197);
}

#nav-bar img {
  width: 200px;
}
</style>
