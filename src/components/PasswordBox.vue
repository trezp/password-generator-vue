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
    background-color: #273549;
    width: 50%;
    height: 3em;
    line-height: 3em;
    border: none;
    margin-right: 1em;
    color: white;
    text-align: center;
    border-radius: 10px;
    font-size: 1.2em;
  }
</style>
  