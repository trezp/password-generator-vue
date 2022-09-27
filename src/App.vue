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
      password2: ''
    }
  },
  methods: {
    getRandomCharacter(arr, max){
      return arr[Math.floor(Math.random() * max)]; 
    },
    generatePassword(charLength){
      let password = '';
      for(let i = 0; i < charLength; i++){
        password += this.getRandomCharacter(characters, this.characters.length);
      }
      return password; 
    },
    getPasswords() {
      this.password1 = this.generatePassword(15);
      this.password2 = this.generatePassword(15);
    }
  }
}
</script>

<template>
  <h1>Generate a <span>Random Password</span></h1>
  <h2>Never use an insecure password again</h2>
  <div class="container">
    <PasswordBox :password="password1" />
    <PasswordBox :password="password2"/>
  </div>
  <button @click="getPasswords">Generate Passwords</button>
</template>

<style scoped>
  .container {
    display: flex;
  }

  h1 span {
    color: green;
  }
</style>
