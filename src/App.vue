<template>
  <div id="app">
        <router-view></router-view>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
  }
}
</script>

<style lang="scss">
*{
    margin: 0;
    padding: 0;
}
#app,html,body{
    height: 100%;
    overflow: hidden;

}
</style>
