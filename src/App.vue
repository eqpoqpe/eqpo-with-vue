<template>
  <div
    id="app"
    @selectstart="
      (e) => {
        e.preventDefault();
      }
    "
  >
    <Logo />
    <div class="console-front">
      <div class="console">
        <Console ref="console" />
      </div>
    </div>
  </div>
</template>

<script>
import StaticFolder from './component/StaticFolder.vue';
import Logo from './component/Logo.vue';
import Console from './component/Console.vue';

export default {
  name: 'App',
  components: { StaticFolder, Logo, Console },
  data() {
    return {
      url: window.location.href,
    };
  },
  mounted() {
    const prev = new Event('prev');
    const next = new Event('next');

    document.addEventListener('keydown', this.userInput);
  },
  methods: {
    userInput(e) {
      if (e.keyCode === 38) this.$refs.console.prevOne();
      if (e.keyCode === 40) this.$refs.console.nextOne();
    },
  },
};
</script>

<style>
body {
  background-color: #202124;
  margin: 0px;
}

* {
  box-sizing: border-box;
}

* pre {
  color: rgb(42, 245, 55);
  cursor: pointer;
}

.wait {
  color: rgb(42, 245, 55, 0.3);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 20px;
  color: #2c3e50;
}

.console-front {
  background: transparent;
  max-width: 800px;
  height: auto;
  margin: 0px auto 0px auto;
}

.console {
  background-color: rgb(0, 0, 0, 0.5);
  border-radius: 15px;
  box-shadow: 0px 0px 10px 0px rgb(0, 0, 0, 0.5);
  width: 97%;
  height: 360px;
  position: relative;
  margin: 0px auto 0px auto;
}

@keyframes blind {
  50% {
    color: transparent;
  }
}

@-webkit-keyframes blind {
  50% {
    color: transparent;
  }
}
</style>
