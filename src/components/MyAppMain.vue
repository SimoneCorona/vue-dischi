<template>
  <div class="main_wrapper">
    <div class="container">
        <div v-if="loading">
            <MyAppLoading />
        </div>
        <div v-else class="row row-cols-6">
            <MyAppTrackCards v-for="element in track_info" :key="element.index" :track="element"/>
        </div>
    </div>
  </div>
</template>

<script>
import MyAppTrackCards from './MyAppTracksCards.vue'
import axios from "axios"
import MyAppLoading from './MyAppLoading.vue';

export default {
    name: 'MyAppMain',
    components: {
    MyAppTrackCards,
    MyAppLoading
},
    data() {
        return {
            track_info: [],
            loading: true,
        }
    },
    created() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((resp) => {
            this.track_info = resp.data.response;
            this.loading = false;
        });
    }    
}
</script>

<style scoped lang="scss">
@import "../style/variables.scss";

.main_wrapper{
  background-color: $brand-secondary-color;
}
</style>