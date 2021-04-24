<template>
  <div class="image-form-container">
    <h3>Choose a file to edit.</h3>
    <form v-on:submit.prevent="onSubmit" class="image-form-">
        <label for="file-selector-default" class="file-selector-label">Browse
        <input type="file" id="file-selector-default" @change="getFile">
        </label>
        <input type="text" id="file-selector-name" placeholder="Filename" v-bind:value="fileName">
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
          console.log(e.target.value);
      }
  }
}
</script>
