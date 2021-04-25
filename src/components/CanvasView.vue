<template>
    <div>
        <h3>Preview</h3>
        <canvas width="400px" height="400px" ref="canvas">{{drawImg()}}</canvas>
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
            },
            drawImg() {
                if (this.$refs.canvas) {
                    console.log('refs:', this.$refs)
                    const ctx = this.$refs.canvas.getContext('2d');
                    console.log('cts:', ctx)
                    }
                }
        }
    }
</script>

<style scoped>
.img-file {
    width: 800px;
}
</style>