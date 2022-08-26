<template>
    <main class="container-fluid m-0 p-0">
        <div class="row row-cols-5 g-3 ms_bg">
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
        }

</style>