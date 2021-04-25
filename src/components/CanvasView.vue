<template>
    <div>
        <h3>Preview</h3>
        {{create(files[0])}}
        <canvas width="400px" height="400px" ref="canvas" class="canvas-preview"></canvas>
    </div>
</template>

<script>
    export default {
        name: 'CanvasView',
        props: {
            files: Array
        },
        
        methods: {
            create(file) {
            if (!file || file === null) {
                    return null;
                }

                const fileUrl = URL.createObjectURL(file);

                // Set image source to new Image() constructor
                const imgFile = new Image();
                imgFile.src = fileUrl;
                console.log('imgFile', imgFile)

                // Run event after image loads
                // imgFile.addEventListener('load', this.drawImg(imgFile));
                imgFile.onload = () => {
                    this.drawImg(imgFile);
                };
                
        },
        drawImg(img) {
            if (this.$refs.canvas && img) {
                const ctx = this.$refs.canvas.getContext('2d');
                console.log('ctx:', ctx)
                // console.log('this', this)
                console.log('drawImage', ctx.drawImage(img, 33, 71, 104, 124, 21, 20, 87, 104));
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