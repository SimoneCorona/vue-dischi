<template>
    <main>
        <div class="main_wrapper">
            <MyAppSearchGenre @filterGenre="selectedGenre($event)"/>
            <div class="container">
                <div v-if="loading">
                    <MyAppLoading />
                </div>
                <div v-else class="row row-cols-6">
                    <MyAppTrackCards v-for="element in filterGenreArray" :key="element.index" :track="element"/>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import MyAppTrackCards from './MyAppTracksCards.vue'
import axios from "axios"
import MyAppLoading from './MyAppLoading.vue';
import MyAppSearchGenre from './MyAppSearchGenre.vue';

export default {
    name: 'MyAppMain',
    components: {
        MyAppTrackCards,
        MyAppLoading,
        MyAppSearchGenre,
    },
    computed: {
        filterGenreArray(){
            const genreSelected = this.track_info.filter((item) =>{
                return item.genre.includes(this.genre)        
            })
            return genreSelected;
        }
    },
    data() {
        return {
            track_info: [],
            loading: true,
            genre: '',
        }
    },
    methods: {
        selectedGenre(userSelectedGenre) {
            this.genre = userSelectedGenre;
        }
    },
    created() {
         axios.get("https://flynn.boolean.careers/exercises/api/array/music")
         .then((resp) => {
             this.track_info = resp.data.response;
             this.loading = false;
             console.log('aaa');
         });
    }
}
</script>

<style scoped lang="scss">
@import "../style/variables.scss";

.main_wrapper{
  background-color: $brand-secondary-color;
  min-height: calc(100vh - 60px);
}
</style>