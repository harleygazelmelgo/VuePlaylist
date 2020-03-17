<template>
    <div class="songplaylist">
        <Song v-for="song in songs" :key="song.artist" :artist="song.artist" :title="song.title"/> 
    </div>
    
</template>

<script>
import Song from './Song.vue'

export default {
    name: 'Songlist',
    components: {
        Song
    },

    props: {
        song: {
            type: Array,
            required: true,
        }
        
    },

    // methods: {}
        
    // data: function() {
    //     return {};
    // }

};

</script>

<style scoped>
    .songplaylist {
        float: left;
        width: 45%;
        border: 1px solid black;
        padding: 10px;
        box-sizing: border-box;
        background: #7CEA9C;

    }
</style>