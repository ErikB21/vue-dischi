<template>
    <div class="col">
        <div class="card text-center p-1 ms_bg_card">
            <img class="car-img-top" :src="disc.poster" :alt="disc.title"/>
            <div class="card-body p-0">
                <h5 class="card-title">{{disc.title}}</h5>
                <div class="card-text">{{disc.author}}</div>
                <div class="card-text">{{disc.year}}</div>
            </div>
        </div>
    </div>  
</template>

<script>
export default {
    name: 'SingleCard',
    props:{
        disc: Object
    }
}
</script>

<style lang="scss">
    @import '../style/general.scss';
    .ms_bg_card{
        background-color: $my_bg_header;
        width: 200px;
    }
</style>