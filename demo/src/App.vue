<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
import 'normalize.css';

export default {
    name: 'app'
};
</script>

<style lang="scss">
$purple: #7b00ff;

html,
body {
    height: 100%;
}

#app {
    font-family: Helvetica, Arial, sans-serif;
    background: $purple;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
