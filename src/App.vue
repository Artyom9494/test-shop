<template>
  <div class="puge">

    <Header></Header>

    <form action="" @submit.prevent>
      <h2>Add product</h2>
      <input v-bind:value="barcode"  @input="barcode = $event.target.value" 
      type="text" class="input" placeholder="barcode">
      <input v-bind:value="price" @input="price = $event.target.value"
      type="text" class="input" placeholder="price">
      <input v-bind:value="name" @input="name =$event.target.value"
      type="text" class="input"  placeholder="name product">

      <button @click="createProduct" class="addButt">addProduct</button>
    </form>

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
      {id:3 , barcode: 80000338798, price: 343, name: "Dos"},
     ],
     barcode: "",
     price: "",
     name: ""
    }
  },
  methods: {
    createProduct() {
      const newProduct = {
        id: Date.now(),
        barcode: this.barcode,
        price: this.price,
        name: this.name
      }
      this.productData.push(newProduct);
      this.barcode = "";
      this.price = "";
      this.name = "";
    }
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
form{
  padding: 5px;
}
.input{
  outline: none;
  margin: 3px;
  padding: 2px;
  border: none;
  border-bottom: solid 2px #2c3e50;
}
.input:focus{
  border-bottom: solid 2px #1f8fff;
}
.addButt{
  padding: 4px;
  border: none;
  border-radius: 4px;
  background:rgb(41, 41, 255);
  color:aliceblue;
  font-weight: 600;
}
</style>
