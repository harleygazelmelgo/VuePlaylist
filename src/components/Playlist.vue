<template>
    <div class="playlist">
        <playSongs v-for="song in songs" :key="song.artist" :artist="song.artist" :title="song.title"/>         
    </div>
    
</template>

<script>
import playSongs from './playSongs.vue'

export default {
    name: 'Playlists',
    components: {
        playSongs
    },

    props: {
        song: {
            type: Array,
            required: true,
        }
        
    },

    methods: {
        RemoveSongFromPlaylist: function(){
            this.$root.$emit ("RemoveSongFromPlaylist", {artist: this.artist, title: this.title})
        }
    }
        
    // data: function() {
    //     return {};
    // }

};

</script>

<style scoped>
    .playlist {
        float: right;
        width: 45%;
        border: 1px solid black;
        padding: 10px;
        box-sizing: border-box;
        background: #70D6FF;

    }
</style>