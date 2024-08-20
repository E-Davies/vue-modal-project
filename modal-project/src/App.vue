<template>
  <h1>{{title}}</h1>
  <div v-if="showDefaultModal">
    <Modal :header="header" :msg="msg" @close="toggleDefaultModal"/>
  </div>
  <div v-if="showSalesModal">
    <Modal header="Sales Modal" msg="This is the message for the sales modal" theme="sale" @close="toggleSalesModal"/>
  </div>
  <button @click="toggleDefaultModal">Default Modal</button>
  <button @click="toggleSalesModal">Sales Modal</button>

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return{
      title: 'My First Vue App',
      header: 'Default Modal ', 
      msg: 'This is the message for the default modal',
      showDefaultModal: false,
      showSalesModal: false
    }
  },
  methods: {
    toggleDefaultModal(){
      this.showDefaultModal = !this.showDefaultModal
    },
    toggleSalesModal(){
      this.showSalesModal = !this.showSalesModal
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  margin: 10px;
}
</style>
