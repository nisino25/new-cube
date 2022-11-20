<template>
  <main>
    <nav class="nav nav1" > 
        <div>
          <a href="/" class="nav-item" data-color="#446A46" >Home</a>
          <a href="/stats" class="nav-item" data-color="#446A46" >Stats</a>
          <a href="/settings" class="nav-item" data-color="#446A46" >Settings</a>
          <span class="nav-indicator"></span>
        </div>
    </nav>

    <router-view />
  </main>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  mounted(){
    // Disable scrolling.
    document.ontouchmove = function (e) {
      e.preventDefault();
    }
  },

}
</script>

<style>
body{
  background-color: #0F4C75;
  color: #BBE1FA;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  touch-action: manipulation;
  /* overflow: hidden;
  position: fixed; */
}

main {
  /* display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center; */
  /* padding: 20px 0; */

  /* background-color: red; */
  margin: 15px auto;
  width: 90vw;
  max-width: 600px;
  /* margin: 15px 0;  */
}

.nav {
  background-color: #BBE1FA;
  display: -webkit-inline-box;
  display: -ms-inline-flexbox;
  display: inline-flex;
  overflow: hidden;
  max-width: 660px;
  min-width: 600px;
  padding: 0 20px;
  border-radius: 20px;
  -webkit-box-shadow: 0 8px 36px rgba(157, 160, 175, 0.8);
  box-shadow: 0 8px 36px rgba(157, 160, 175, 0.8);

  display: inline-block;
  overflow: hidden;
  position: relative;
  height: 50px;

  display: flex;
  justify-content: center;
  align-items: center;

}
.nav-item {
  color: #1B262C;
  padding: 30px 20px;
  text-decoration: none;
  -webkit-transition: 0.3s;
  -o-transition: 0.3s;
  transition: 0.3s;
  margin: 0 6px;
  z-index: 1;
  font-family: "Open Sans", sans-serif;
  font-weight: 700;
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
