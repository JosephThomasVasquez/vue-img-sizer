<template>
  <div class="image-form-container">
    <h3>Choose a file to edit.</h3>
    <form v-on:submit.prevent="onSubmit" class="image-form-">
        <label for="file-selector-default" class="file-selector-label">Browse
        <input type="file" id="file-selector-default" @change="getFile" multiple>
        </label>
        <input type="text" id="file-selector-name" placeholder="Filename" v-bind:value="fileName">
    </form>
    <FilesList v-bind:files="files !== undefined ? files : null"/>
    
  </div>
</template>

<script>

import FilesList from './FilesList.vue';

export default {
  name: 'ImageForm',
  data() {
      return {
          fileName: 'Filename',
          files: []
      }
  },
  methods: {
      getFile(e) {
          console.log(e.target.value);
          console.log(e.target.files);
          return this.files = [...e.target.files];
      }
  },
  components: {
      FilesList
  }
}
</script>
