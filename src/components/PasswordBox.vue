<script>
  export default {
    props: ['password']
  }
</script>
  
<template>
  <div class="password-field">{{password}}</div>
</template>

<style scoped>
  .password-field {
    background-color: lightgray;
    width: 50%;
    height: 3em;
    line-height: 3em;
    border: none;
    margin: 1em;
    color: black;
    border-radius: 10px;
  }
</style>
  