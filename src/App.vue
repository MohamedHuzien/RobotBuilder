<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li class="nav-item">
            <img class="logo" src="./assets/logo.png"/> Build-a-bot
            </li>
        </ul>
      </nav>
    </header>
    <main>
      <RobotBuilder/>
    </main>
  </div>
</template>

<script>
import HomePage from './Home/HomePage.vue';
import RobotBuilder from './Builder/RobotBuilder.vue'

export default {
  name: 'app',
  components: {
    HomePage,
    RobotBuilder
  },
};
</script>

<style>
body {
  background: linear-gradient(to bottom, #555 , #999);
  background-attachment: fixed;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}

main {
  margin: 0 auto;
  width: 1024px;
  min-height: 300px;
  padding: 30px 0;
  background: white;
}

header {
  background-color: #999;
  width: 1084px;
  margin: 0 auto;
}
ul {
  padding: 3px;
  display: flex;
}
.nav-item {
  display: inline-block;
  padding: 5px 10px;
  font-size: 22px;
  border-right: 1px solid #bbb;
}
.logo {
  vertical-align: middle;
  height: 30px;
}
</style>
