<template>
  <nav class="header">
    <ul>
      <li><a href="/" className="nav-links">Home</a></li>
      <li><a href="/" className="nav-links">Reset</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Header',
}
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
