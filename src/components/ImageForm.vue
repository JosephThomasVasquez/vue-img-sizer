<template>
  <div class="image-form">
    <h1>{{ msg }}</h1>
    <form>
        <input type="file" name="" id="">
    </form>
    
  </div>
</template>

<script>
export default {
  name: 'ImageForm',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
