<script>

import PasswordBox from './components/PasswordBox.vue';
import characters from './characters.js';

export default {
  components: {
    PasswordBox
  },
  data() {
    return {
      password1: '',
      password2: '',
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
      this.password1 = this.generatePassword();
      this.password2 = this.generatePassword();
    }
  }
}
</script>

<template>
  <h1>Generate a <span>Random Password</span></h1>
  <h2>Never use an insecure password again</h2>
  <button @click="getPasswords" class="btn-password">Generate Passwords</button>
  <div class="container-pw-display">
    <PasswordBox :password="password1" />
    <PasswordBox :password="password2"/>
  </div>
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
