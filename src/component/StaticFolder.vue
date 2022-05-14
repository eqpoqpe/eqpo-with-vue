<template>
  <div class="folder">
    <pre>
  ____
 | ___|_
 |/____/
 {{ name }}
    </pre>
  </div>
</template>

<script>
export default {
  name: 'Folder',
  props: ['name'],
};
</script>

<style scoped>
.folder {
  display: inline-flex;
  margin: 0px 20px 0px 20px;
}

.folder pre {
  color: rgb(42, 245, 55);
  cursor: pointer;
}
</style>
