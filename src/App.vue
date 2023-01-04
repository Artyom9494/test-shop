<template>
  <div class="puge">
    <Header></Header>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/header/header.vue"
import Footer from "../src/components/header/footer/footer.vue"

export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.puge{
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
