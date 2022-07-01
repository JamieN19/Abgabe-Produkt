<template>
  <nav>
    <router-link to="/HomeView">Home</router-link> |
    <router-link to="/ReservationsView">Reservations</router-link> |
    <router-link to="/AboutView">About</router-link>
  </nav>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #6d1000;
}

button {
  border-bottom: 2px solid #6d1000;
  background-color: #6d1000;
  border: none;
  color: white;
  border-radius: 1.2em;
  padding: 0.4em;
  margin: 1em;
}
input[type="text"],input[type="date"], select {
  padding: 0.4em;
  border: none;
  border-bottom: 2px solid #6d1000;
  font: inherit;
}
label {
  text-align:  right;
}
label::after {
  content: ":";
}
</style>
