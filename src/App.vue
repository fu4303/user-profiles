<template>
  <main id="app">
  <header>
    <h1> Random User Profiles </h1>
    <p> Vue Demo app for AXIOS </p>
    <p> Api : Random Users </p>
  </header>
    <user-profiles></user-profiles>
    <footer>
      Created by FAE
    </footer>
  </main>
</template>

<script>
import UserProfiles from './components/UserProfiles.vue'


export default {
  name: 'App',
  components: {
    UserProfiles
  }
}
</script>

<style>
*{
  margin:0px;
  padding:0px;
}
body {
  background-color: #161616;
}

header h1{
    text-align: center;
    color:white;
    font-size: 50px;
    margin-bottom: 20px;
}
header p{
    text-align: center;
    color:white;
    
}
footer{
  color:white;
  text-align: right;
  background-color: #8d9d6e;
  padding:20px;
}
</style>
