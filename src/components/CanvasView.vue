<template>
    <div>
        <h3>Preview</h3>
        
        <canvas width="800px" height="400px" ref="canvas" class="canvas-preview">{{createUrl(files[0])}}</canvas>
    </div>
</template>

<script>
    export default {
        name: 'CanvasView',
        props: {
            files: Array
        },
        data() {
            return {
                canvas: null,
                context: null,
                getFiles: this.files
            }
        },
        mounted() {
           
        },
        methods: {
            createUrl(file) {
                if (!file || file === null) {
                    return null;
                }
                
                const fileUrl = URL.createObjectURL(file);
                console.log('1. Creating url >', fileUrl)
                return this.drawImg(fileUrl)
            },
            drawImg(url) {
            
                // Set image source to new Image() constructor
                let imgFile = new Image();
                imgFile.src = url;
                console.log('2. Creating image w/ src >', imgFile)
                

                // Run event after image loads
                // imgFile.addEventListener('load', this.drawImg(imgFile));
                imgFile.onload = () => {
                    console.log('3. Loaded img >', imgFile)
                    const ctx = this.$refs.canvas.getContext('2d');
                    console.log('ctx:', ctx)
                    console.log('drawImage', ctx.drawImage(imgFile, 0, 0, 104, 124, 21, 20, 87, 104));
                    ctx.drawImage(imgFile, 0, 0, 200, 100);
                };
        }
        }
    }
</script>

<style scoped>
.img-file {
    width: 800px;
}
</style>