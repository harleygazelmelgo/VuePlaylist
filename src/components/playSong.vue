<template>
    <div class="playSongs">
        <p>{{ artist }}</p>
        <p>{{ title }}</p>
        <button v-on:click="removeSong">Remove from playlist</button>
    </div>

</template>

<script>

export default {
    name: "playSong",
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
        removeSong: function(){
            this.$root.$emit ("removeSong", {artist: this.artist, title: this.title})
        }
        
    },
}

</script>



<style scoped>
    .playSongs {

        float: right;
        height: 15vh;
        width: 20vw;
        border: 1px solid black;
        padding: 10px;
        box-sizing: border-box;
        color:blue;

    }
    
</style>