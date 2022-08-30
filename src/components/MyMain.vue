<template>
    <main class="container-fluid g-0 ms_bg">
        <LoadProgress v-if="loadProgress"/>
        
        <div v-else class="d-block d-sm-flex align-items-center flex-wrap m-auto ms_wi">
            <SingleCard v-for="disc in filterDisc" :key="disc.id" :disc="disc"/>
        </div>

    </main>
</template>

<script>

import axios from 'axios';
import SingleCard from './SingleCard.vue';
import LoadProgress from './LoadProgress.vue';

export default {
    name: "MyMain",

    components: {
        SingleCard,
        LoadProgress
    },
    
    props:{
        genereRicercato: String
    },

    computed:{
        filterDisc(){
            if(this.genereRicercato == ''){
                return this.discList
            }else{
                const arrayDisc = this.discList.filter(disc =>{
                    if(disc.genre == this.genereRicercato){
                        return true;
                    }else{
                        return false
                    }
                });
                return arrayDisc;
            }
        }
    },

    data(){
        return{
            discList: [],
            api: 'https://flynn.boolean.careers/exercises/api/array/music',
            loadProgress: true,
            genres:[]
        }
    },

    mounted(){
        this.getDiscMusic();
    },

    methods:{
        getDiscMusic(){
            axios.get(this.api)
            .then(response =>{
                // console.log(response);
                this.discList = response.data.response;
                console.log(this.discList)

                this.discList.forEach(disc =>{
                    if(!this.genres.includes(disc.genre)){
                        this.genres.push(disc.genre);
                    }
                });

                this.$emit('genresReady', this.genres);

                this.loadProgress = false;
                console.log(this.loadProgress)
            })
            .catch(err => {
                console.log(err);
                this.loadProgress = false;
            });
        }
    }
}
</script>

<style scoped lang="scss">
    @import '../style/general.scss';
    .ms_bg{
            background-color: $my_bg_main;
            height: 90vh;
            overflow-y: scroll;
            .ms_wi{
                width: 70%;
                padding-top: 30px;
            }
        }

</style>