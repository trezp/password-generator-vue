<script>

import PasswordBox from './components/PasswordBox.vue';
import characters from './characters.js';

export default {
  components: {
    PasswordBox
  },
  data() {
    return {
      passwords: ['', ''],
      passLength: 15
    }
  },
  methods: {
    getRandomChar(arr){
      return arr[Math.floor(Math.random() * arr.length)]; 
    },
    generatePassword(passLength = this.passLength){
      let password = '';
      for(let i = 0; i < passLength; i++){
        password += this.getRandomChar(characters);
      }
      return password; 
    },
    getPasswords() {
      this.passwords = [];
      this.passwords.push(this.generatePassword());
      this.passwords.push(this.generatePassword());
    }
  }
}
</script>

<template>
  <h1>Generate a <span>Random Password</span></h1>
  <h2>Never use an insecure password again</h2>
  <button @click="getPasswords" class="btn-password">Generate Passwords</button>
  <ul class="container-pw-display">
    <PasswordBox :password="password" v-for="password in passwords" :key="password" />
  </ul>
</template>

<style scoped>
  h1 {
    font-family: 'Karla', sans-serif;
    font-weight: 800;
  }

  h1 span {
    color: #F43F5E;
    display: block;
  }

  h2 {
    color: #D5D4D8;
  }
  .container-pw-display {
    padding: 0; 
    display: flex;
  }
  .btn-password {
    margin: 1.5em 0 2em 0;
    color: #fff;
    background: #F43F5E;
    border-radius: 6px;
    width: 191px;
  }

</style>
