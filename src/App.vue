<template>
  <div id="app">
    <Songlist : songs= "songs"/>  
            
    <Playlist : songs= "playSongs"/>

  </div>
</template>

<script>
import Songlist from './components/Songlist.vue'
import Playlist from './components/Playlist.vue'


export default {
  name: 'App',
  components: {
    Songlist,
    Playlist,
  },
  created() {
        this.$root.$on("addSong", this.addSongToPlaylist);
        this.$root.$on("removeSong", this.removeSongFromPlaylist);
  },

  data: function() {
    return {
      songs: [ 
                {
                  artist:'Bill Withers', 
                  title:'Lovely Day'
                },

                {
                  artist:'Blackstreet', 
                  title:'In a rush' 
                },

                {
                  artist:'Dexys Midnight Runners',
                  title:'Come on Eileen',
                },
                  
                {
                  artist:'Renee Dominique', 
                  title:'Could I love you anymore'
                },

                {
                  artist:'Labrinth', 
                  title:'Jealous'
                },

                {
                  artist:'Matisyahu', 
                  title:'One day' 
                },

                {
                  artist:'Lionel Richie',
                  title:'Easy',
                },
                  
                {
                  artist:'Miguel', 
                  title:'Sure thing'
                }

              ],
              playSongs: []
    };
  }
  
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
