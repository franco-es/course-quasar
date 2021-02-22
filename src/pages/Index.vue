<template>
  <q-page padding>
    <input type="text" 
      v-model="message" 
      @keyup.esc="ClearMessage" 
      @keyup.enter="AlertMessage"
    />
    <button @click="ClearMessage">Clear</button>
    <h5>{{message}}</h5>
  </q-page>
</template>

<script>
export default {
  data(){
    return {
      message: 'I love VueJs so Hard!'
    }
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
</style>
