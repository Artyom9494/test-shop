<template>
  <div class="puge">
    <Header></Header>
    <div class="wrrap">
      <div v-for="proData in productData" class="dataBlock">
        <span>Баркод: {{proData.barcode}}</span>
        <p>Цена: {{proData.price}}</p> 
        <p>Наименование: {{proData.price}}</p>  
      </div>
    </div>
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
  },
  data() {
    return {
     productData: [
      {id:1 , barcode: 80000365647, price: 43, name: "Doshic"},
      {id:2 , barcode: 80000261243, price: 423, name: "shic"},
      {id:3 , barcode: 80000338798, price: 343, name: "Dos"}
     ]
    }
  },
  methods: {
    
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
  min-height: 100vh;
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
.dataBlock{
  padding: 4px;
  border-top: solid #2c3e5046 2px;
  border-bottom: solid #2c3e5046 2px; 
  display: flex;
  justify-content:space-around;
  justify-items: center;
  font-weight: 800;
}
.wrrap{
  overflow: hidden;
  height: 91vh;
}
</style>
