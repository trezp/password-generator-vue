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
      numOfChars: '15'
    }
  },
  methods: {
    getRandomChar(arr){
      return arr[Math.floor(Math.random() * arr.length)]; 
    },
    generatePassword(charLength){
      let password = '';
      for(let i = 0; i < charLength; i++){
        password += this.getRandomChar(characters);
      }
      return password; 
    },
    getPasswords() {
      this.password1 = this.generatePassword(this.numOfChars);
      this.password2 = this.generatePassword(this.numOfChars);
    }
  }
}
</script>

<template>
  <h1>Generate a <span>Random Password</span></h1>
  <h2>Never use an insecure password again</h2>
  <div class="container-pw-display">
    <PasswordBox :password="password1" />
    <PasswordBox :password="password2"/>
  </div>
  <label for="numOfChars" class="label-password">Password Length:</label>
  <select v-model="numOfChars" id="numOfChars" class="select-password">
    <option value="10">10</option>
    <option value="15" selected>15</option>
    <option value="20">20</option>
  </select>
  <button @click="getPasswords" class="btn-password">Generate Passwords</button>
</template>

<style scoped>
  body {
    font-family: 'Karla', sans-serif;
  }
  .container-pw-display {
    display: flex;
  }

  h1 {
    font-weight: 800;
    font-size: 40px;
  }

  h1 span {
    color: #E11D48;
  }
  .label-password {
    font-size: 18px;
    font-weight: bold;
    display: block;
  }

  .select-password {
    width: 25%;    
    padding: .75em;
    border-radius: 5px;
  }

  .btn-password {
    display: block;
    margin: 1.5em auto;
  }
</style>
