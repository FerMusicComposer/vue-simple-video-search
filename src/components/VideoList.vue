<template>
    <ul>
        <VideoListItem></VideoListItem>
    </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue'
export default ({
    name: 'VideoList',
    components: {
        VideoListItem
        },
    props: {
        videos: Array
    }
})
</script>

<style>

</style>
