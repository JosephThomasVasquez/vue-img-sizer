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
        this.ctx = this.$refs.canvas.getContext("2d");
        this.ctx.fillStyle ="#5ec"
        this.ctx.fillRect(10, 20, 150, 100)
        console.log('this.ctx >', this.ctx)
        },
        methods: {
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
                this.ctx.clearRect(0, 0, 400, 300)
                // console.log('3. Loaded img >', img);
                // let canvas = this.$refs.canvas;
                // let ctx = canvas.getContext("2d");
                // ctx.fillStyle ='#777';
                // ctx.fillRect(10, 20, 150, 100)
                // console.log('4. Get canvas context >', ctx);
                console.log('5. DrawImage to canvas >', img, 0, 0, img.width, img.height);
                this.ctx.drawImage(img, 0, 0, img.width, img.height);
            }
        }
    }
</script>
