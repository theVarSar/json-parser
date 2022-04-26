<template>
  <NavBar/>
  <!-- <img alt="Muscular Nerd" class="logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Favourite online Tool"/> -->
  <TextEditor/>
</template>

<script>
import NavBar from './components/NavBar.vue'
// import HelloWorld from './components/HelloWorld.vue'
import TextEditor from './components/Texteditor.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld,
    NavBar,
    TextEditor
  },
  mounted(){
    // CodeMirror.fromTextArea(document.getElementById('editor'),{
    //   lineNumbers: true
    // })
  }
}
</script>

<style>
/* .logo {
  width: 100px;
} */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.CodeMirror {
    border: 1px solid #eee; 
    height: auto; 
}
</style>
