<script>

import PasswordBox from './components/PasswordBox.vue';

const characters = ["A","B","C","D","E","F","G","H","I","J","K","L","M","N","O","P","Q","R","S","T","U","V","W","X","Y","Z","a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z", "0", "1", "2", "3", "4", "5", "6", "7", "8", "9","~","`","!","@","#","$","%","^","&","*","(",")","_","-","+","=","{","[","}","]",",","|",":",";","<",">",".","?","/"]

function getRandomCharacter(max){
  return characters[Math.floor(Math.random() * max)]; 
}

function generatePassword(charLength){
  let password = '';
  for(let i = 0; i < charLength; i++){
    password += getRandomCharacter(characters.length);
  }
  return password; 
}

export default {
  components: {
    PasswordBox
  },
  data() {
    return {
      password1: generatePassword(15),
      password2: generatePassword(15)
    }
  }
}
</script>

<template>
  <h1>Generate a <span>Random Password</span></h1>
  <h2>Never use an insecure password again</h2>
  <div class="container">
    <PasswordBox password="password1" />
    <PasswordBox password="password2"/>
  </div>
  <button @click="generatePasswords">Generate Passwords</button>
</template>

<style scoped>
</style>
