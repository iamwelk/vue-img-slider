<template>
  <div class="hello">
    <div v-for="(item, index) in list" :key="item" class="item" :style="{left: (600 * (index - currentIndex)) + 'px'}">
      <div class="content" :style="{backgroundColor: colors[index]}">{{item}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      list: [1, 2, 3, 4],
      colors: ['#c1e194', '#a5c669', '#70ae7d', '#2d9594'],
      currentIndex: 0
    }
  },
  mounted () {
    setInterval(() => {
      this.currentIndex = (this.currentIndex + 1) % 4
    }, 2000)
  }
}
</script>

<style lang="scss" scoped>
  .hello {
    position: relative;
    width: 600px;
    height: 200px;
    margin: 0 auto;
    overflow: hidden;;
  }
  .item {
    position: absolute;
    width: 600px;
    height: 200px;
    padding: 10px;
    box-sizing: border-box;

    .content {
      display: flex;
      width: 100%;
      height: 100%;
      background: #ccc;
      justify-content: center;
      align-items: center;
    }
  }
</style>
