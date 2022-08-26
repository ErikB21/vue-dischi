<template>
    <main class="container-fluid g-0 ms_bg">
        <div class="d-block d-sm-flex align-items-center flex-wrap m-auto ms_wi">
            <SingleCard v-for="disc in discList" :key="disc.id" :disc="disc"/>
        </div>
    </main>
</template>

<script>

import axios from 'axios';
import SingleCard from './SingleCard.vue';

export default {
    name: "MyMain",
    components: { 
        SingleCard 
    },
    data(){
        return{
            discList: [],
            api: 'https://flynn.boolean.careers/exercises/api/array/music', 
        }
    },
    mounted(){
        this.getDiscMusic();
    },
    methods:{
        getDiscMusic(){
            axios.get(this.api)
            .then(response =>{
                console.log(response);
                this.discList = response.data.response;
            })
            .catch(err => {
                console.log(err);
            });
        }
    }
}
</script>

<style scoped lang="scss">
    @import '../style/general.scss';
    .ms_bg{
            background-color: $my_bg_main;
            .ms_wi{
                width: 70%;
                padding-top: 30px;
            }
        }

</style>