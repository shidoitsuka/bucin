<template>
  <div :style="'background:' + (darkMode() ? '#171717' : '#f5f5f5')">
    <vue-particles
      class="particles"
      :color="darkMode() ? '#f5f5f5' : '#171717'"
      :particleOpacity="0.7"
      :particlesNumber="50"
      shapeType="circle"
      :particleSize="4"
      linesColor="#dedede"
      :linesWidth="1"
      :lineLinked="true"
      :lineOpacity="0.4"
      :linesDistance="150"
      :moveSpeed="3"
      :hoverEffect="true"
      hoverMode="grab"
      :clickEffect="true"
      clickMode="push"
    />
    <div class="main">
      <vue-typed-js
        :showCursor="false"
        :strings="[greetings() + ', ' + nicknames + '!']"
      >
        <h1 class="typing" :style="'color:' + (darkMode() ? '#f5f5f5' : '#171717')"></h1>
      </vue-typed-js>
    </div>
  </div>
  <!-- <v-btn fab icon color="red" class="musicPlayer">
        <v-icon>mdi-play</v-icon>
      </v-btn>
      <video src="https://www.youtube.com/watch?v=bu_86J8gbmA"></video> -->
</template>

<script>
export default {
  transition: "slide-x-transition",
  data() {
    return {
      // prettier-ignore
      nicknames: this.random(["Ava", "Babe", "Sayang", "Avakuu", "Cintuu"]),
      greetings: function() {
        const now = new Date().getHours();
        if (now > 18) return "Good Evening";
        if (now > 15) return "Good Afternoon";
        if (now > 11) return "Good Day";
        if (now > 5) return "Good Morning";
        if (now > 0) return "Good Night";
      },
      darkMode: function() {
        const now = new Date().getHours();
        if (now > 18) return true;
        if (now > 15) return false;
        if (now > 11) return false;
        if (now > 5) return false;
        if (now > 0) return true;
      }
    };
  },
  methods: {
    random: function(arr) {
      return arr[Math.floor(Math.random() * arr.length)];
    }
  }
};
</script>

<style lang="scss">
h1 {
  font-family: "Pacifico", cursive;
}
.main {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-flow: column;
}
.typing {
  margin-top: -50%;
}
/*.musicPlayer {
  position: fixed;
  bottom: 3vh;
  right: 5vw;
}*/
.particles canvas {
  width: 100%;
  height: 100%;
  position: absolute;
}
</style>
