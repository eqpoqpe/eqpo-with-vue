<template>
  <div class="folder">
    <Extend v-if="isClose" @click="isClose = !isClose" />
    <Close v-else="isClose" @click="isClose = !isClose" />
  </div>
</template>

<script>
export default {
  name: 'Folder',
  props: ['name'],
  data() {
    return {
      isClose: true,
    };
  },
  components: {
    Extend: {
      name: 'Extend',
      data() {
        return {
          name: this.$parent.$props.name,
        };
      },
      template: `
<pre>
  ____
 |____|
 |____|
 {{ name }}
</pre>
`,
    },
    Close: {
      name: 'Close',
      data() {
        return {
          name: this.$parent.$props.name,
        };
      },
      template: `
<pre>
  ____
 | ___|_
 |/____/
 {{ name }}
</pre>
`,
    },
  },
};
</script>

<style scoped>
.folder {
  display: inline-flex;
  margin: 0px 20px 0px 20px;
}

.folder pre {
  color: green;
  cursor: pointer;
}
</style>
