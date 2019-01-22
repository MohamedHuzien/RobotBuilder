<template>
  <main>
    <div class="home">
      <div>
         <img class="robot" src="../assets/robot-home.png"/>
      </div>
      <div class="get-started"> 
        <a href="">Get Started </a> Building you first robot
      </div>
    </div>
  </main>
</template>

<script>
import RobotBuilder from './../Builder/RobotBuilder.vue'
export default {
  name: 'HomePage',
  props: {
  },
  components : {
    RobotBuilder
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.home {
text-align: center;
}
.robot {
  height: 300px;
}

</style>
