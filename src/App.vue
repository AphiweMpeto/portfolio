<template>
  <div>
        <div>
            <router-link to="/">Home</router-link>
        </div>
    <div class="app">
    <Navigation/>
    </div>
    <router-view/>
  </div>

</template>

<script>
import Navigation from "./components/Navigation.vue"
export default {
  name:'App',
  components:{
    Navigation
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Tangerine:bold,bolditalic|Inconsolata:italic|Droid+Sans");
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Raleway", sans-serif;
  font-weight: 400;
}

.app {
  min-height: 100vh;
  position: relative;
  background-color: #f1f1f1;
}
.container {
  padding: 0 20px;
  max-width: 1140px;
  margin: 0 auto;
}
</style>
