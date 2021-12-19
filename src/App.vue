<template>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList :videos="videos"></VideoList>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar.vue'
import VideoList from './components/VideoList.vue'
const API_KEY = 'AIzaSyBeQJ8pPHVcvMFMxWpfNovK5ZsiMQiUOkU'

export default ({
    name: 'App',
    components: {
        SearchBar,
        VideoList
    },
    data() {
        return {
            videos: []
        }
    },
    methods: {
        async onTermChange(searchTerm) {
            try {
                const response = await axios.get('https://www.googleapis.com/youtube/v3/search', {
                    params: {
                        key: API_KEY,
                        type: 'video',
                        part: 'snippet',
                        q: searchTerm
                    }
                })
                this.videos = response.data.items;
                console.log(this.videos)
            } catch (err) {
                console.log(err)
            }   
        }
    }
})
</script>
