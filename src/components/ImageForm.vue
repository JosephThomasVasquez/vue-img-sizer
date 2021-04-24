<template>
  <div class="image-form">
    <h3>Choose a file to edit.</h3>
    <form>
        <button>
        <input type="file" name="" id="file-selector" @change="getFile" hidden>Browse</button>
        <input type="text" name="" id="" placeholder="Filename" v-bind:value="fileName">
    </form>
    
  </div>
</template>

<script>
export default {
  name: 'ImageForm',
  data() {
      return {
          fileName: 'Filename'
      }
  },
  methods: {
      getFile(e) {
          return e.target.value
      }
  }
}
</script>
