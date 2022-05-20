<template>
  <div class="track_card">
      <img :src="track.poster" alt=""> 
      <h1>{{ track.title }}</h1>
      <p>{{ track.author }}</p>
      <p>{{ track.year }}</p>
  </div>
</template>

<script>
export default {
    name: 'MyAppTracksCards',
    props: {
        track: Object,
    },
}
</script>

<style scoped lang="scss">
@import "../style/variables.scss";

.track_card{
    background-color: $brand-primary-color;
    text-align: center;
    margin: 2rem 1rem;
    padding: 1rem;

    img{
        width: 100%;
        padding-bottom: 1rem;
    }
    h1{
        color: white;
        font-size: 1.2rem;
        text-transform: uppercase;
    }
    p{
        color: grey;
        margin: 0 auto;
    }
}
</style>