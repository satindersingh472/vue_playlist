<template>
<!-- all is the parent div -->
  <div class="all">
    <!-- h1 is the heading -->
    <h1>List of Songs</h1>
<!-- list div will have a list  of songs -->
    <div class="list" ref="all_songs">
        <!-- list item is every songs that is in the list -->
      <div
        class="list_item"
        v-for="song in songs"
        :key="song[`id`]"
     
      >
      <!-- items div will contain all the information about song in the list and if we click on the div there is an event calling current song function -->
        <div class="items"    @click="current_song">
          <h2>Song: {{ song[`title`] }}</h2>
          <h2>Singer: {{ song[`artist`] }}</h2>
          <p>Song_Id: {{ song[`song_id`] }}</p>
          <img :src="song[`image_url`]" :alt="song[`song_id`]" />
        </div>
      </div>
    </div>
    <!-- display playing div will contain the current song -->
      <div class="display_playing">
        <h2>playing song</h2>
        <div ref="song_playing"></div>
      </div>
  </div>
</template>

<script>
export default {
    // methods will contain functions
  methods: {
    // current song will get details[`outerHTML] of clicked items and show them inside ref song playing 
    current_song(details) {
        this.$refs[`song_playing`][`innerHTML`] = details[`target`][`parentElement`][`outerHTML`];    
        
    }
  },
  data() {
    return {
        // songs is an array of objects containing list of various songs
      songs: [
        {
          title: `peed`,
          artist: `Karaj Randhawa`,
          song_id: `001`,
          image_url: `https://cover.djpunjab.is/52286/300x700/Peed-Karaj-Randhawa.jpg`,
        },
        {
          title: `saanjh`,
          artist: `Romey Maan`,
          song_id: `002`,
          image_url: `https://cover.djpunjab.is/52277/300x700/Saanjh-Romey-Maan.jpg`,
        },
        {
          title: `A class`,
          artist: `K.S Makhan`,
          song_id: `003`,
          image_url: `https://cover.djpunjab.is/52275/300x700/A-Class-Ks-Makhan.jpg`,
        },
      ],
    };
  },
};
</script>

<style scoped>
* {
  text-align: center;
}
img {
  height: 100px;
  width: 100px;
}
.list {
  display: grid;
  order: 2;
  grid-template-columns: 1fr 1fr 1fr;
}
.list_item {
  display: grid;
  grid-template-columns: auto;
  justify-self: center;
  padding: 10px 10px 20px 20px;
  box-shadow: 3px 3px 6px grey;
}
.items {
    font-size: 1rem;
  display: grid;
  align-items: center;
  justify-items: start;
}
.all{
    display: grid;
    text-align: center;
}
h1{
    order: 2;
}
.display_playing{
    order: 1;
    text-align: center;
    display: grid;
    place-items: center;
}
</style>