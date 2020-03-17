<template>
    <div class="Song">
        <p>{{ artist }}</p>
        <p>{{ title }}</p>
        <button v-on:click="addSong">Add to playlist</button>
    </div>

</template>

<script>

export default {
    name: "Song",
    props: {
        artist: {
            type: String,
            required: true,
        },
        title: {
            type: String,
            required: true,
        }
    },
    methods: {
        addSong: function(){
            this.$root.$emit ("addSong", {artist: this.artist, title: this.title})
        }
        
    }
};

</script>

<style scoped>

    .Song {

        float: left;
        height: 15vh;
        width: 20vw;
        border: 1px solid black;
        padding: 10px;
        box-sizing: border-box;
        color: darkmagenta;

    }
    
</style>