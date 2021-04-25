<template>
    <div>
        <h3 v-if="files.length !== 0">{{files.length}} Files</h3>
        <ul>
            <li v-for="file in files" v-bind:key="file">
                <div class="file-preview">
                <picture>
                    <source media="(min-width: 650px)" class="img-preview" v-bind:srcset="listFiles(file)">
                    <source media="(min-width: 465px)" class="img-preview" v-bind:srcset="listFiles(file)">
                    <img class="img-preview" v-bind:src="listFiles(file)">
                </picture>
                {{file.name}} {{file.type}} {{fileSize(file.size)}}
                </div></li>
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
            listFiles(file) {
                
                if (!file || file === null) {
                    return null;
                }

                const fileUrl = URL.createObjectURL(file);
                console.log(fileUrl)
                return fileUrl;
            }
        }
    }
</script>