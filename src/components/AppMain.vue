<script>
import {store} from "../store"
import AppCard from "./AppCard.vue";

export default{
    name: "AppMain",
    data(){
        return{
            store
        }
    },
    components:{
        AppCard,
    },
}
</script>

<template>
    <main v-if="store.movies.length > 0">
        <div class="container">
            
            <!-- movies search -->
            <h2>Movies</h2>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 g-3">
                <div class="col" v-for="(movie, index) in store.movies" :key="index">
                    <AppCard :item="movie"/>
                </div>
            </div>
            <!-- /movies search-->

            <!-- shows search-->
            <h2>Shows</h2>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 g-3">

                <div class="col" v-for="(show, index) in store.shows" :key="index">
                    <AppCard :item="show"/>
                </div>
            </div>
            <!-- /shows search-->

        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../style/general.scss" as *;
main{
    height: 85vh;
    overflow-y: scroll;
    .container{
        .row{
            padding-bottom: 2rem;
        }
        h2{
            font-size: 2.6rem;
            padding: .8rem 0;
        }
    }
}
main::-webkit-scrollbar{
    display: none;
}
</style>
