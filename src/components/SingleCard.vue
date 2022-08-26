<template>
    <div class="d-flex flex-column text-center p-4 align-items-center ms_bg_card">
        <div class="ms_box">
            <img class="" :src="disc.poster" :alt="disc.title"/>
        </div>
        <div class="ms_h p-0">
            <h4 class="ms_color_1">{{disc.title}}</h4>
            <div class="ms_color_2">{{disc.author}}</div>
            <div class="ms_color_2">{{disc.year}}</div>
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
        background-color: $my_bg_header!important;
        max-width: calc(100% / 5 - 20px);
        max-height: 350px;
        margin: 10px 10px;
        .ms_box{
            height: 200px;
            img{
                width: 100%;
            }
        }
        .ms_h{
            height: 140px;
            .ms_color_1{
                color: $my_color_title;
            }
            .ms_color_2{
                color: $my_color_span;
            }
        }
    }
</style>