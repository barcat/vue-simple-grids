<template>
  <div id="app">
    <simple-grids :numberOfRows="20" :numberOfColumns="3" :lineHeight="20" :rowSpace="10" :columnSpace="5">
    </simple-grids>
  </div>
</template>

<script>
import simpleGrids from './components/simple-grids';

export default {
  name: 'app',
  components: {
    simpleGrids,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
  margin-left: 20px;
  margin-right: 20px;
}
</style>
