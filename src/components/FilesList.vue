<template>
    <div>
        <h3 v-if="files.length !== 0">{{files.length}} Files</h3>
        <ul>
            <li v-for="file in files" v-bind:key="file">{{file.name}} {{file.type}} {{fileSize(file.size)}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'FilesList',
        props: {
            files: Array
        },
        methods: {
            fileSize(size, decimals) {
                if (size === 0) return '0 Bytes';
                const k = 1024;
                const dm = decimals < 0 ? 0 : decimals;
                const sizes = ['Bytes', 'KB', 'MB', 'GB', 'TB', 'PB', 'EB', 'ZB', 'YB'];
                const i = Math.floor(Math.log(size) / Math.log(k));
                return parseFloat((size / Math.pow(k, i)).toFixed(dm)) + ' ' + sizes[i];
            },
            listFiles(files) {
                if (!files || files === null) {
                    return 'No Files';
                }
                return files.map((file) => {
                    console.log(file)
                        file.name
                    })
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>