<template>
    <div>
        <h3>{{files.length}} Files</h3>
        <ul>
            <li>{{files[0].name}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'FilesList',
        props: {
            files: Array
        }
    }
</script>

<style lang="scss" scoped>

</style>