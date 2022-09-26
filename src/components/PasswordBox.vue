<script>
  export default {
    props: ['password']
  }
</script>
  
<template>
  <input type="text" :value="password" class="password-field"/>
</template>

<style scoped>
  .password-field {
    background-color: blue;
    width: 100%;
    border: none;
  }
</style>
  