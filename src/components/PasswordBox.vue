<script>
  export default {
    props: ['password']
  }
</script>
  
<template>
  <li class="password-field">
    {{ password }}
  </li>
</template>

<style scoped>
  .password-field {
    list-style-type: none;
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
  