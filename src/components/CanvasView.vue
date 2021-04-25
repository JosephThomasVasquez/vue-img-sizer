<template>
    <div>
        <h3>Preview</h3>
        <div width="400px" height="400px"><img class="img-file" v-bind:src="createUrl(files[0])"></div>
    </div>
</template>

<script>
    export default {
        name: 'CanvasView',
        props: {
            files: Array
        },
        methods: {
            createUrl(file) {
                
                if (!file || file === null) {
                    return null;
                }

                

                const fileUrl = URL.createObjectURL(file);

                // Set image source to new Image() constructor
                const imgFile = new Image();
                imgFile.src = fileUrl;

                // Run event after image loads
                imgFile.addEventListener('load', () => {
                    console.log('Image loaded', imgFile)
                }, false);

                console.log(fileUrl)
                return fileUrl;
            }
        }
    }
</script>

<style scoped>
.img-file {
    width: 800px;
}
</style>