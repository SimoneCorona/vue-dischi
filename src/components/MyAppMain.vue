<template>
  <div class="main_wrapper">
    <div class="container">
        <div class="row row-cols-6">
            <MyAppTrackCards v-for="element in track_info" :key="element.index" :track="element"/>
        </div>
    </div>
  </div>
</template>

<script>
import MyAppTrackCards from './MyAppTracksCards.vue'
import axios from "axios"

export default {
    name: 'MyAppMain',
    components: {
        MyAppTrackCards,
    },
    data() {
        return {
            track_info: [],
        }
    },
    created() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((resp) => {
            this.track_info = resp.data.response;
            console.log(resp.data.response)
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