<script>

import PasswordBox from './components/PasswordBox.vue';

export default {
  components: {
    PasswordBox
  },
  data() {
    return {
      characters: ["A","B","C","D","E","F","G","H","I","J","K","L","M","N","O","P","Q","R","S","T","U","V","W","X","Y","Z","a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z", "0", "1", "2", "3", "4", "5", "6", "7", "8", "9","~","`","!","@","#","$","%","^","&","*","(",")","_","-","+","=","{","[","}","]",",","|",":",";","<",">",".","?","/"],
      password1: '',
      password2: ''
    }
  },
  methods: {
    getRandomCharacter(max){
      return this.characters[Math.floor(Math.random() * max)]; 
    },
    generatePassword(charLength){
      let password = '';
      for(let i = 0; i < charLength; i++){
        password += this.getRandomCharacter(this.characters.length);
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
</style>
