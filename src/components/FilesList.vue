<template>
    <div>
        <h3 v-if="files.length !== 0">{{files.length}} Files</h3>
        <ul>
            <li v-for="file in files" v-bind:key="file">{{file.name}} {{file.type}} {{file.size}}</li>
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