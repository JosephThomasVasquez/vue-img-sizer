<template>
    <div>
        {{drawImg(files[0])}}
        <h3>Preview</h3>
        <canvas width="800px" height="400px" id="canvas" ref="canvas" class="canvas-preview"></canvas>
    </div>
</template>

<script>
    export default {
        name: 'CanvasView',
        props: {
            files: Array
        },
        mounted() {
        //    this.getFiles !== null && this.drawImg(this.Files)
        //    console.log(this.files)
        },
        methods: {
            // createUrl(file) {
            //     if (!file || file === null) {
            //         return null;
            //     }
                
            //     const fileUrl = URL.createObjectURL(file);
            //     console.log('1. Creating url >', fileUrl)
            //     return this.drawImg(fileUrl)
            // },
            drawImg(file) {
                    if (!file || file === null) {
                    return null;
                }
 
            let reader = new FileReader();
            console.log('reader', reader)
 
            reader.onload = (e) => {
               let imgFile = new Image();
                imgFile.onload = () => {
                     this.updateCanvas(imgFile);
                }
                imgFile.src = e.target.result;
            };
 
            reader.readAsDataURL(file);
            },
            updateCanvas(img) {
                
                console.log('3. Loaded img >', img);
                let canvas = this.$refs.canvas;
                let ctx = canvas.getContext("2d");
                console.log('4. Get canvas context >', ctx);
                // console.log('5. DrawImage to canvas >', ctx.drawImage(img, 0, 0, img.width, img.height));
                ctx.drawImage(img, 0, 0, img.width, img.height);
            }
        }
    }
</script>

<style scoped>
.img-file {
    width: 800px;
}
</style>