<template>
  <Header />
  <Title msg="Image Resizer"/>
  <ImageForm/>
</template>

<script>
import Header from './components/Header.vue';
import Title from './components/Title.vue';
import ImageForm from './components/ImageForm.vue';


export default {
  name: 'App',
  components: {
    Header,
    Title,
    ImageForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
