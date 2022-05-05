<template>
  <div class="AlbumContainer d-flex justify-content-space-around my-4">
      <img :src="song.poster" alt="" class="w-100 my-3">
      <div class="AlbumTitle my-2">
          <h3 class="FSize text-white">{{song.title}}</h3>
      </div>
      <div class="AlbumDescription">
          <p>{{song.author}}</p>
          <p>{{song.year}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name:'AlbumComp',
    props:{
        song : Object,
    },
}
</script>

<style lang="scss" scoped>
    .AlbumContainer{
        background-color: #2E3A46;
        flex-wrap: wrap;
        flex-direction: column;

        p{
            line-height: 5px;
        }
       
    }

    .AlbumDescription{
        color: #6b7880;
    }
    .AlbumTitle{
        color: #808078;
    }

    .FSize{
        font-size: 20px;
        font-weight: 600;
    }
</style>