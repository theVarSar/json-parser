<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>Paste your JSON so that we can put makeup on it....</p>
      <div class="container">
        <textarea class="form-control rounded-0" id="input-area" rows="10"></textarea>  
      </div><br>
      <button v-on:click="ParseIt" class="btn btn-default">Beautify the shit out of it</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    ParseIt(){
      let a= document.getElementById("input-area").value
      console.log(a)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
