<template>
  <div class="logo">
    <pre>
      <code>
                   . \      <span class="use-blind">☄️</span> ' /.
  ___  __ _ _ __   _`'   <span class="use-blind">☄️</span>  `'__   ___ 
 / _ \/ _` | '_ \ / _ <span class="use-blind">☄️</span>   `./ '_ \/ _ \
|  __/ (_| | |_) | (_) | (_| | |_) |  __/
 \___|\__, | .__/ \___/ \__, | .__/ \___|
          | | |            | | |
          |_|_|            |_|_|
      </code>
    </pre>
  </div>
</template>

<script>
/* eslint-disable */

export default {
  name: 'Logo',
  components: {},
};
</script>

<style scoped>
.logo {
  width: fit-content;
  height: fit-content;
  margin: 0px auto 0px auto;
}

.logo pre {
  color: rgb(42, 245, 55);
  cursor: pointer;
}

.use-blind:nth-child(1) {
  -webkit-animation: blind 900ms;
  animation: blind 900ms;
  animation-iteration-count: infinite;
  -webkit-animation-iteration-count: infinite;
}

.use-blind:nth-child(2) {
  -webkit-animation: blind 900ms;
  animation: blind 900ms;
  -webkit-animation-delay: 150ms;
  animation-delay: 150ms;
  -webkit-animation-iteration-count: infinite;
  animation-iteration-count: infinite;
}

.use-blind:nth-child(3) {
  -webkit-animation: blind 900ms;
  animation: blind 900ms;
  -webkit-animation-delay: 200ms;
  animation-delay: 200ms;
  -webkit-animation-iteration-count: infinite;
  animation-iteration-count: infinite;
}
</style>
