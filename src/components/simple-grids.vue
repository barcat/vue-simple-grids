<template>
  <div class="simple-grids" :style="gridOpt">
    <slot></slot>
    <div class="mock-cell" :key="key" v-for="(mock, key, index) in mocksList" :id="'mock-'+ key" :style="{gridColumnStart: mock.c, gridColumnEnd: mock.c + 1, gridRowStart: mock.r, gridRowRnd: mock.r + 1}"> x </div>
  </div>
</template>
<script>
export default {
  props: {
    numberOfRows: Number,
    numberOfColumns: Number,
    lineHeight: Number,
    rowSpace: Number,
    columnSpace: Number,
  },
  computed: {
    gridOpt() {
      return {
        gridTemplateRows: `repeat(${this.numberOfRows}, ${this.lineHeight}px)`,
        gridTemplateColumns: `repeat(${this.numberOfColumns}, ${100 / this.numberOfColumns}%)`,
        lineHeight: `${this.lineHeight}px`,
        gridRowGap: `${this.rowSpace}px`,
        gridColumnGap: `${this.rowSpace}px`,
      };
    },
    mocksList() {
      const arr = [];
      for (let c = 1; c <= this.numberOfColumns; c += 1) {
        for (let r = 1; r <= this.numberOfRows; r += 1) {
          arr.push({ c, r });
        }
      }
      // eslint-disable-next-line
      // console.log(arr);
      return arr;
    },
  },
};
</script>
<style scoped>
.simple-grids {
  display: grid;
}

.mock-cell {
  background-color: orange;
  opacity: 0.2;
}
</style>
