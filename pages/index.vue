<template>
  <div :class="darkMode() ? 'darkBG' : 'lightBG'">
    <vue-particles
      class="particles"
      :color="darkMode() ? '#f5f5f5' : '#171717'"
      :particleOpacity="0.7"
      :particlesNumber="30"
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
    <audio src="~/assets/music.ogg" autoplay controls />
    <div class="main">
      <!-- prettier-ignore -->
      <vue-typed-js
        class="vue-typed"
        :showCursor="false"
        :loop="true"
        :strings="[greetings() + ', ' + nicknames + '! ^5000', 'I always wanted to tell you... ^2500', 'Nevermind! >///<']"
        :backDelay="500"
        :typeSpeed="100"
        :backSpeed="20"
        :contentType="'null'"
      >
        <h1 class="typing"></h1>
      </vue-typed-js>
      <h2 class="quotes quotes-main">{{ quotes.quotes }}</h2>
      <h3 class="quotes author">{{ quotes.author }}</h3>
    </div>
  </div>
</template>

<script>
import quotesFile from "~/assets/quotes.js";
if (process.browser) {
  function random(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
  }
  window.onNuxtReady(app => {
    document.addEventListener("click", function(ev) {
      const x = ev.clientX;
      const y = ev.clientY;
      let el = document.createElement("div");
      el.innerHTML = `<h1>${random(["♥", "♥♥", "♥♥♥"])}</h1>`;
      el.classList.add("popup");

      el.style.left = `${x}px`;
      el.style.top = `${y}px`;
      document.body.appendChild(el);
      setTimeout(function() {
        el.style.display = "none";
      }, 3000);
    });
  });
}
export default {
  transition: "slide-x-transition",
  data() {
    return {
      // prettier-ignore
      nicknames: this.random(["Ava", "Babe", "Sayang", "Avakuu", "Cintuu"]),
      quotes: this.random(quotesFile),
      greetings: function() {
        const now = new Date().getHours();
        if (now > 18) return "Good Evening";
        if (now > 15) return "Good Afternoon";
        if (now > 11) return "Good Day";
        if (now > 5) return "Good Morning";
        if (now >= 0) return "Good Night";
      },
      darkMode: function() {
        const now = new Date().getHours();
        if (now > 18) return true;
        if (now > 15) return false;
        if (now > 11) return false;
        if (now > 5) return false;
        if (now >= 0) return true;
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
.darkBG,
.lightBG {
  width: 100vw;
}
.darkBG {
  background: linear-gradient(137deg, #2d1f3d, #614385, #516395, #6b82c2);
  background-size: 800% 800%;
  color: #121829;

  -o-webkit-animation: darkGradient 11s ease infinite;
  -o-moz-animation: darkGradient 11s ease infinite;
  animation: darkGradient 11s ease infinite;
}
.lightBG {
  background: linear-gradient(137deg, #ffc3a0, #ffafbd, #dd5e89);
  background-size: 600% 600%;
  color: #4f3d3f;

  -o-webkit-animation: lightGradient 8s ease infinite;
  -o-moz-animation: lightGradient 8s ease infinite;
  animation: lightGradient 8s ease infinite;
}
audio {
  display: none;
}
.particles canvas {
  width: 100%;
  height: 100%;
  position: absolute;
}
.main {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-flow: column;
}
.typing {
  font-family: "Lilita One", cursive;
  font-size: 2.1rem;
  text-align: center;
}
.vue-typed {
  min-height: 4em;
}
.quotes {
  font-family: "Montserrat", sans-serif;
  text-align: center;
}
.quotes-main {
  font-size: 1.1rem;
}
.author {
  font-size: 0.7rem;
}
.popup {
  display: block;
  text-align: center;
  width: 100px;
  height: 40px;
  position: absolute;
  margin-left: -50px;
  margin-top: -40px;
  background: transparent;
  animation: fadeIn linear 1s;
  -o-webkit-animation: fadeIn linear 1s;
  -o-moz-animation: fadeIn linear 1s;
  opacity: 0;
}
/*.musicPlayer {
  position: fixed;
  bottom: 3vh;
  right: 5vw;
}*/

@-webkit-keyframes lightGradient {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@-moz-keyframes lightGradient {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@keyframes lightGradient {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}

@-webkit-keyframes darkGradient {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@-moz-keyframes darkGradient {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@keyframes darkGradient {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}

@keyframes fadeIn {
  50% {
    opacity: 1;
  }
  100% {
    margin-top: -100px;
  }
}

@-webkit-keyframes fadeIn {
  50% {
    opacity: 1;
  }
  100% {
    margin-top: -100px;
  }
}

@-moz-keyframes fadeIn {
  50% {
    opacity: 1;
  }
  100% {
    margin-top: -100px;
  }
}
</style>
