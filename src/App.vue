<template>
  <div class="wrapper">
    <nav class="nav nav1" > 
        <div>
          <a href="/" class="nav-item" data-color="#446A46" >Home</a>
          <a href="/settings" class="nav-item" data-color="#446A46" >Settings</a>
          <span class="nav-indicator"></span>
        </div>
    </nav>

    <button @click="topFunction()" id="myBtn" title="Go to top" :style="showing ? 'opacity: 1;' : 'opacity: 0;'">&#8593;</button>

  </div>
  <router-view />
</template>

<script>

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
body{
  background-color: #eee;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  
  /* text-align: center; */
  /* color: #E94560; */
  
}

.wrapper {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  padding: 20px 0;

  

  /* background-color: red; */

  
}
.nav {
  /* float: right; */
  display: -webkit-inline-box;
  display: -ms-inline-flexbox;
  display: inline-flex;
  overflow: hidden;
  max-width: 660px;
  min-width: 600px;
  /* background-color: #fff; */
  /* background-color: red; */
  padding: 0 20px;
  border-radius: 20px;
  -webkit-box-shadow: 0 8px 36px rgba(157, 160, 175, 0.8);
  box-shadow: 0 8px 36px rgba(157, 160, 175, 0.8);

  display: inline-block;
  overflow: hidden;
  position: relative;
  height: 50px;

  display: flex;
  justify-content: space-between;
  align-items: center;


  
  /* height: 200px; */
  /* border: 3px solid green;  */
  /* background-color: red; */
}
.nav-item {
  color: #83818c;
  padding: 30px 20px;
  text-decoration: none;
  -webkit-transition: 0.3s;
  -o-transition: 0.3s;
  transition: 0.3s;
  margin: 0 6px;
  z-index: 1;
  font-family: "Open Sans", sans-serif;
  font-weight: 700;
  /* text-align: right; */

  /* background-color: red; */
  /* float: right; */
}
.nav-item:before {
  content: "";
  position: absolute;
  -webkit-transition: 0.3s;
  -o-transition: 0.3s;
  transition: 0.3s;
}
.nav-item:not(.active):hover:before {
  opacity: 1;
  bottom: 0;
}
.nav-item:not(.active):hover {
  color: #333;
}
.nav-indicator {
  position: absolute;
  bottom: 0;
  -webkit-transition: 0.4s;
  -o-transition: 0.4s;
  transition: 0.4s;
  height: 5px;
  z-index: 1;
}
.nav1 .nav-indicator {
  height: 5px;
  left: 0;
  border-radius: 8px 8px 0 0;
}
.nav1 .nav-item:before {
  bottom: -6px;
  left: 0;
  border-radius: 8px 8px 0 0;
  -webkit-transition: 0.3s;
  -o-transition: 0.3s;
  transition: 0.3s;
}

@media (max-width: 992px) {
  .wrapper {
    padding: 20px 0 15px;
  }
}

@media only screen and (max-width: 768px) {
  .nav {
    min-width: 90%;
  }
  .nav1 {
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
  }
  .nav-item {
    padding: 20px 10px;
  }
}
@media (max-width: 580px) {
  .nav1 {
    -webkit-box-pack: start;
    -ms-flex-pack: start;
    justify-content: flex-start;
    overflow-x: auto;
  }
}


</style>
