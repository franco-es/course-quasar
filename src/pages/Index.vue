<template>
  <q-page padding>
    <button
    style="position: absolute; right:10px;"
    @click="counter++"

    >
      {{counter}}
    </button>
    <input type="text" 
      v-model="message" 
      @keyup.esc="ClearMessage" 
      @keyup.enter="AlertMessage"
    />

    <button @click="ClearMessage">Clear</button>

    <h5 
    class="border-grey" 
    v-if="message.length">{{message}}
    </h5>
    <h6 v-else>No message entered 🤔</h6>

    <hr>

    <p>messaje to UPPERCASE <b v-if="message.length">{{messadeUppercase}}</b><b v-else>No hay mensaje para mostrar</b></p>
  </q-page>
</template>

<script>
export default {
  data(){
    return {
      message: 'I love VueJs so Hard!',
      counter: 0
    }
  },
  computed:{
    // los metodos computados no son funciones tecnicamente, pero se escriben igual.
    messadeUppercase(){ return this.message.toUpperCase() }
    
  },
  methods: {
    ClearMessage() {
      this.message = '';
    },
    AlertMessage(){
      alert(this.message);
    }
    
  }
}
</script>
<style>
.border-grey{
  border: 1px solid grey;
}
</style>
