<template>
  <div id="app">
    <div v-for="message in messages" :key="message.text">
      <h4>{{ message.title }}</h4>
      <p>{{ message.text }}</p>
      <p>{{ message.timestamp }}</p>
    </div>
  </div>
</template>

<script>

import Firebase from 'firebase'

// Initialize Firebase
var config = {
  apiKey: 'AIzaSyDYHUb6VgMd5_TRr3kgCnSXnRUsHy_4Biw',
  authDomain: 'vuebootfb.firebaseapp.com',
  databaseURL: 'https://vuebootfb.firebaseio.com',
  projectId: 'vuebootfb',
  storageBucket: 'vuebootfb.appspot.com',
  messagingSenderId: '211213444616'
}

let app = Firebase.initializeApp(config)

let db = app.database()
let messagesRef = db.ref('message')

export default {
  name: 'app',
  firebase: {
    messages: messagesRef
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
