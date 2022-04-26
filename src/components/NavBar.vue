<template>
<nav class="navbar navbar-inverse navbar-fixed-top">
    <div class="container-fluid">
    <div class="navbar-header">
        <a class="navbar-brand" href="#">Muscular Nerd</a>
    </div>
    <ul class="nav navbar-nav navbar-right">
      <li><a href="#">Docs</a></li>
      <li><a href="#">Feedback</a></li>
      <li><a href="#">About</a></li>
    </ul>
  </div>
</nav>
</template>

<script>
export default {
  name: "NavBar",
//   props: {
//     msg: String,
//   }
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
